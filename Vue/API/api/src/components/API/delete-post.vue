<template>
  <div>
    <h1>delete</h1>
    <table>
      <tr>
        <td>Id</td>
        <td>Title</td>
        <td>Author</td>
        <td>Action</td>
      </tr>
      <tr v-for="item in posts" :key="item.id">
        <td>{{item.id}}</td>
        <td>{{item.title}}</td>
        <td>{{item.author}}</td>
        <td><button @click="deletePost(item.id)">Delete</button></td>
      </tr>
    </table>
  </div>
</template>
<script>
import Vue from "vue";
import VueAxios from "vue-axios";
import axios from "axios";
Vue.use(VueAxios, axios);
export default {
    methods:{
        getPostData(){
            Vue.axios.get("http://localhost:3000/posts").then(res=>{
                this.posts=res.data
                // console.log(res)
            })
        },
        deletePost(id){
            Vue.axios.delete("http://localhost:3000/posts/"+id).then(res=>{
                // this.posts=res.data
                console.log(res)
                this.getPostData()
            })
        }
    },
    mounted(){
        this.getPostData()
    },
    data(){
        return{
            posts:null
        }
    }
};
</script>
<style scoped>
table {
  text-align: center;
  border: 3px solid;
  stroke:blue;
}
</style>