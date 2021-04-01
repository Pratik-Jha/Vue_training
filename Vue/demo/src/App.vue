<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <!-- <HelloWorld msg="Welcome to Your Vue.js App" /> -->
  <!-- <Home/> -->
  <!-- <conditional>
    <template v-slot:header><h2>Header</h2></template>
    <template v-slot:main><h2>main</h2></template>
    <template v-slot:footer></template>
  </conditional> -->
  <!-- <child greet="Hello Everyone" :user="user" :showAlert="showAlert" id="childCmp"><h1>Slot Demo</h1></child> -->
  <!-- <Form/> -->
  <!-- <navbar v-on:eventCall="display($event)"></navbar>
  <p>{{ title }}</p> -->
  <list-data/>
</template>

<script>
import ListData from './components/API/list-data.vue';
// import HelloWorld from "./components/HelloWorld.vue";
// import Home from "./components/Home.vue";
// import Conditional from './components/conditional.vue';
// import Navbar from "./components/Navbar/navbar.vue";
// import Child from "./components/child.vue";
// import Form from './components/Form/form.vue';

export default {
  name: "App",
  components: {
    ListData
    // Child,
    // Form,
    // HelloWorld,
    // Home,
    // Conditional,
    // Navbar,
  },
  data() {
    return {
      title: "Pratik",
      user: {
        Name: "Vaibhav Mishra",
        age: 23,
      },
    };
  },
  methods: {
    showAlert() {
      alert("Button  click.");
    },
    display() {
      this.title = "Pratik Jha";
    },
  },
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
