<template>
  <div>
    <h1>List data</h1>
    <div>
      <table border="5px">
        <tr>
          <td>Name</td>
          <td>Username</td>
          <td>Email</td>
        </tr>
        <tr v-for="user in users" :key="user.id">
          <td>{{ user.name }}</td>
          <td>{{ user.username }}</td>
          <td>{{ user.email }}</td>
        </tr>
      </table>
    </div>
  </div>
</template>
<script>
import Vue from "vue";
import VueAxios from "vue-axios";
import axios from "axios";
Vue.use(VueAxios, axios);
export default {
  data() {
    return {
      users: undefined,
    };
  },
  mounted() {
    Vue.axios.get("https://jsonplaceholder.typicode.com/users").then((resp) => {
      this.users = resp.data;
      // console.log(resp.data);
    });
  },
};
</script>

<style scoped>
table {
  text-align: center;
  margin-left: 500px;
}
</style>