<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <p>
      For a guide and recipes on how to configure / customize this project,<br />
      check out the
    </p>
    <h2>{{ user }}</h2>
    <p>{{ text }}</p>
    <button @click="sayhello">Say Hello</button>

    <h2>{{ sayhello1(message) }}</h2>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  model: {
    prop: "title",
    event: "change",
  },
  props: {
    msg: String,
    // this allows using the `value` prop for a different purpose
    value: String,
    // use `title` as the prop which take the place of `value`
    title: {
      type: String,
      default: "Default title",
    },
  },
  data() {
    return {
      text: this.sayhello(),
      message: "This is my first component uesing binding data",
    };
  },
  methods: {
    sayhello1(text) {
      return text.toUpperCase();
    },
    sayhello() {
      return "xin chào các bạn";
    },
  },

  inject: ["user"],
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
