<template>
  <!-- <h3>{{ user }}</h3> -->
  <ul>
    <li v-for="item in error" :key="item">{{ item }} Is required.</li>
  </ul>
  <form>
    <input
      type="text"
      placeholder="Enter your Email"
      v-model="user.email"
    /><br /><br />
    <input
      type="password"
      placeholder="Enter your Password"
      v-model="user.password"
    />
    <p v-if="error.item=='password'">required</p>
    <br /><br />
    <select v-model="user.country">
      <option value="">Select Country</option>
      <option value="India">India</option>
      <option value="Australia">Australia</option>
      <option value="others">others</option>
    </select>
    <h4>language you know</h4>
    <label for="">English</label>
    <input type="checkbox" value="English" v-model="user.language" />
    <label for="">Hindi</label>
    <input type="checkbox" value="Hindi" v-model="user.language" />
    <label for="">Guajrati</label>
    <input type="checkbox" value="Gujarati" v-model="user.language" />
    <h4>Gender</h4>
    <label for="male">Male</label>
    <input
      type="radio"
      id="male"
      name="gender"
      value="Male"
      v-model="user.gender"
    />
    <label for="female">Female</label>
    <input
      type="radio"
      id="female"
      name="gender"
      value="Female"
      v-model="user.gender"
    />
    <br /><br />
    <button v-on:click="getValue()" type="button">Submit</button>
  </form>
</template>
<script>
export default {
  name: "form",
  data() {
    return {
      user: {
        email: "",
        password: "",
        country: "",
        language: [],
        gender: "",
      },
      error: [],
    };
  },
  methods: {
    getValue() {
      this.error = [];
      for (const item in this.user) {
        if (this.user[item] === "" || this.user[item].length === 0) {
          this.error.push(item);
        }
      }
      if (this.error.length === 0) {
        alert("Form Submitted.");
      }
      console.log(this.error);
    },
  },
};
</script>