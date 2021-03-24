<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <input type="text" placeholder="Enter Email" v-model="email" /><br /><br />
    <input type="password" placeholder="Enter Password" v-model="password"/><br /><br />
    <button v-on:click="getValue()">Get values</button><br><br>
    <hr>
    <h3>Which js framework is best?</h3>
    <label for="vue">Vue</label>
    <input type="checkbox" value="Vue" name="vue" v-model="framework" id="vue">
    <label for="angular">Angular</label>
    <input type="checkbox" value="Angular" name="angular" v-model="framework" id="angular">
    <label for="react">React</label>
    <input type="checkbox" value="React" name="react" v-model="framework" id="react"><br>
    <h4>The best js framework: {{framework}}</h4>
    <h3>Your role?</h3>
    <label for="student">Student</label>
    <input type="radio" name="role" v-model="role" value="Student" id="student">
    <label for="developer">Developer</label>
    <input type="radio" name="role" v-model="role" value="Developer" id="developer"><br>
    <h4>Your Role is: {{role}}</h4>
    <hr>

  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  data() {
    return {
      email: null,
      password: null,
      framework:[],
      role:null,
      show:true
    };
  },
  props: {
    msg: String,
  },
  methods: {
    getValue() {
      console.log("Value: ", this.email, this.password);
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1 {
  color: aquamarine;
}
hr{
  color: cadetblue;
  width: 1;
}
</style>
