<template>
  <div class="about">
    <h1>This is an about page</h1>
    <p>Full name {{ fullname }}</p>
    <input type="text" v-model="fullname" />

    <p>Last Name {{ lastname }}</p>
    <!-- <child v-model:name="fullname" v-model:name1="lastname"></child> -->
  </div>
  <div>
    <p>Parent :{{ value }}</p>
    <button @click="onclick">Click</button>
    <child @click="onclick" v-model:value="value"></child>
  </div>
</template>
<script>
import Child from "../components/Child.vue";

export default {
  name: "About",
  components: {
    Child,
  },
  data() {
    return {
      // name:['hung','nam','phi'],
      newName: "",
      fullname: "lee zet",
      firstname: "lee",
      lastname: "zet",
      value: 0,
    };
  },
  methods: {
    onclick() {
      this.value++;
      console.log(this.value);
    },
  },
};
</script>
<style scoped>
.about li {
  list-style: none;
}
</style>

