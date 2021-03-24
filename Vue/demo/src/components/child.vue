<template>
  <h1>{{ greet }}</h1>
  <h2>
    Name: <u>{{ user.Name }}</u> Age: {{ user.age }}
  </h2>
  <button v-on:click="showAlert()">Click</button>
  <div :class="applyStyle" v-on:mousemove="classStyle = !classStyle">
    <h2>Hover me.</h2>
  </div>
</template>

<script>
export default {
  data() {
    return {
      classStyle: true,
    };
  },
  props: {
    greet: String,
    user: Object,
    showAlert: Function,
  },
  computed: {
    applyStyle() {
      return {
        font_size: this.classStyle,
      };
    },
  },
};
</script>

<style scoped>
.font_size {
  font-size: 20px;
  color: crimson;
}
</style>