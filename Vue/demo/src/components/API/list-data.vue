<template>
  <h1>List data</h1>
</template>
<script>
import Vue from "vue";
import VueAxios from "vue-axios";
import axios from "axios";
Vue.use(VueAxios, axios);
export default {
  mounted() {
    Vue.axios.get("https://jsonplaceholder.typicode.com/users").then((resp) => {
      console.log(resp);
    });
  },
};
</script>