<template>
  <div>
    <input type="text" placeholder="Enter the title" v-model="post.title" />
    <input
      type="text"
      placeholder="Enter the Author"
      v-model="post.author"
    /><br />
    <button @click="postSubmit()">Submit</button>
  </div>
</template>
<script>
import Vue from "vue";
import axios from "axios";
import vueAxios from "vue-axios";
Vue.use(vueAxios, axios);
export default {
  data() {
    return {
      post: {
        author: null,
        title: null,
      },
    };
  },
  methods: {
    // getPostData() {
    //   Vue.axios.get("http://localhost:3000/posts").then((res) => {
    //     this.posts = res.data;
    //     console.log(res);
    //   });
    // },
    postSubmit() {
      Vue.axios.post("http://localhost:3000/posts", this.post).then((res) => {
        console.log(res);
        // this.getPostData();
      });
    },
  },
};
</script>