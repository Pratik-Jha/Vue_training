<template>
  <h5 v-if="show">If</h5>
  <h5 v-else>Else</h5>
  <button v-on:click="show = !show">Change</button>
  <hr />
  <h3>Showing data using looping statement.</h3>
  <ul >
    <li v-for="item in technology" :key="item">{{ item }}</li>
  </ul>
  <ul>
    <li v-for="item in user" :key="item">
      Email is {{ item.email }} and mobile number is {{ item.mobile }}
    </li>
  </ul>
</template>
<script>
export default {
  name: "conditional",
  data() {
    return {
      show: true,
      technology: ["Java", ".net", "js"],
      user: [
        {
          email: "pratik@gmail.com",
          mobile: 7888552211,
        },
        {
          email: "shipra@gmail.com",
          mobile: 7888552211,
        },
        {
          email: "Navin@gmail.com",
          mobile: 7888552211,
        },
      ],
    };
  },
};
</script>