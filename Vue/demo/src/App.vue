<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <!-- <HelloWorld msg="Welcome to Your Vue.js App" /> -->
  <!-- <Home/> -->
  <!-- <conditional/> -->
  <child greet="Hello Everyone" :user="user" :showAlert="showAlert" id="childCmp"/>
  <!-- <Form/> -->
</template>

<script>
// import HelloWorld from "./components/HelloWorld.vue";
// import Home from "./components/Home.vue";
// import Conditional from './components/conditional.vue';
import Child from "./components/child.vue";
// import Form from './components/Form/form.vue';

export default {
  name: "App",
  components: {
    Child,
    // Form,
    // HelloWorld,
    // Home,
    // Conditional,
  },
  data() {
    return {
      user: {
        Name: "Vaibhav Mishra",
        age: 23,
      },
    };
  },
  methods:{
    showAlert(){
      alert("Button  click.")
    }
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  color: #2c3e50;
  margin-top: 60px;
}
</style>
