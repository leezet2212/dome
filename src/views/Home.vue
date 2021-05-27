<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" />
    <HelloWorld msg="you are welcome" />
    <ul v-for="names in name" :key="names.index">
      <li>{{ names }}</li>
    </ul>
    <input type="text" v-model="newName" />
    <button @click="onclick()">add name</button>

    <div>
      <p>test</p>
      <span>{{ messagebook }}</span>
      <br />
      <span>{{ mesage }}</span>
      <p>đảo ngược :{{ isrevesed }}</p>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from "@/components/HelloWorld.vue";

export default {
  name: "Home",
  components: {
    HelloWorld,
  },
  data() {
    return {
      mesage: "đây là thuộc tính đảo ngược !",
      author: {
        name: "John Doe",
        books: [
          "Vue 2 - Advanced Guide",
          "Vue 3 - Basic Guide",
          "Vue 4 - The Mystery",
        ],
      },
      name: [],
      newName: "",
    };
  },
  computed: {
    isrevesed() {
      return this.mesage.split("").reverse().join("");
    },
    messagebook() {
      return this.author.books.length > 0 ? "yes" : "no";
    },
  },
  provide: {
    user: `leezet`,
  },
  methods: {
    onclick() {
      this.name.push(this.newName);
      this.newName = "";
    },
  },
};
</script>
