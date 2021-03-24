<template>
  <!-- ******* when we want only single value. ********* -->
  <!--<p>Email: {{ getAlldata(23).email }}</p> 
  <p>Mobile: {{ getAlldata(23).mobile }}</p> -->
  <html>
    <body>
      <p>Email: {{ email }}</p>
      <p>Age: {{ getAge(28) }}</p>
      <p>All data: {{ getAlldata() }}</p>
      <button v-on:click="count()">Click Me</button>
      <h3 v-on:mousemove="getValue()">Hover on me.</h3>
      <h4>{{ cnt }}</h4>
      <input type="text" v-model="textValue" /><br />
      type in the above textbox to see value here: {{ textValue }}
    </body>
  </html>
</template>

<!--****************** Script ************************-->
<script>
export default {
  data() {
    return {
      email: "pratik@gmail.com",
      cnt: 0,
      textValue: "",
    };
  },
  methods: {
    getAge(age) {
      return age;
    },
    getAlldata() {
      return {
        email: this.email,
        mobile: "784569222",
      };
    },
    count() {
      this.cnt = this.cnt + 1;
    },
    getValue() {
      console.warn("hover");
    },
  },
};
</script>

<!--********************** Style *********************-->
<style scoped>
p {
  color: blue;
}
</style>
