<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <!-- <list-data/> -->
    <!-- <post-form/> -->
    <ul>
      <li>
        <router-link to="/">Add Post</router-link>
      </li>
      <li>
        <router-link to="/delete">Delete Post</router-link>
      </li>
    </ul>
    <router-view></router-view>
    <!-- <delete-post /> -->
  </div>
</template>

<script>
// import DeletePost from "./components/API/delete-post.vue";
// import PostForm from './components/API/postForm.vue'
// import ListData from './components/API/list-data.vue'

export default {
  name: "App",
  components: {
    // PostForm,
    // ListData
    // DeletePost,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
