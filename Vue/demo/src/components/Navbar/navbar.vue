<template>
  <h2>{{ name }}</h2>
  <div>
    <button class="btn btn-primary" @click="tab = 'home'">Home</button>
    <button class="btn btn-success" @click="tab = 'ContactUs'">
      Contact Us
    </button>
    <button class="btn btn-danger" @click="tab = 'AboutUs'">About Us</button>
    <button @click="changeName()">Get fullname</button>
    <component :is="tab" />
  </div>
</template>
<script>
import AboutUs from "./about-us.vue";
import ContactUs from "./contact-us.vue";
import home from "./home.vue";
export default {
  components: { home, ContactUs, AboutUs },
  name: "navbar",
  data() {
    return {
      name: "navbar",
      tab: "ContactUs",
    };
  },
  methods: {
    changeName() {
      this.$emit("eventCall", "navbar");
    },
  },
};
</script>