<template>
  <!--Here i bind the non-props property to this tag. -->
  <h1 v-bind="$attrs">{{ greet }}</h1>
  <h2>
    Name: <u>{{ user.Name }}</u> Age: {{ user.age }}
  </h2>
  <button v-on:click="showAlert()">Click</button>
  <div
    :class="applyStyle"
    v-on:mousemove="classStyle = !classStyle"
    style="width: 150px"
  >
    <h2>Hover me.</h2>
  </div>
  <hr />
  <h3>Ref Example.</h3>
  <input type="number" ref="demoRef" v-model.number="textValue" /><br />
  {{ textValue }}
  <br /><br />
  <h4>If you have dare increase the below value more then 5.😎</h4>
  {{ countValue }} <br />
  <button @click="countValue = countValue + 1">+</button>
  <button @click="countValue = countValue - 1">-</button><br /><br />
  <button v-on:click="getRefvalue()">Submit</button>
</template>

<script>
export default {
  data() {
    return {
      classStyle: true,
      textValue: "",
      countValue: 0,
    };
  },
  props: {
    greet: String,
    user: Object,
    showAlert: Function,
  },
  watch: {
    countValue(cur, old) {
      if (cur > 5 && cur > old) {
        alert(
          "Opps,you are trying to increase the value more then 5 but it not possible😝"
        );
        this.countValue = 0;
      }
    },
  },
  computed: {
    applyStyle() {
      return {
        font_size: this.classStyle,
      };
    },
  },
  methods: {
    getRefvalue() {
      if (this.$refs.demoRef.value.length < 6) {
        this.$refs.demoRef.style.color = "red";
      } else {
        this.$refs.demoRef.style.color = "green";
      }
      console.log(this.$refs.demoRef.value);
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