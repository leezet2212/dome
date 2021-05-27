<template>
  <div class="child">
    <p>Children :{{ value }}</p>
    <br />
    <button @click="onclickchild">ClickChild</button>
    <!-- <input
      type="text"
      :value="name"
      @input="$emit('update:name', $event.target.value)"
    />
    <input
      type="text"
      :value="name1"
      @input="$emit('update:name1', $event.target.value)"
    />
  </div> -->
    <!-- <div class="container">
    <div v-for="name in namechild" :key="name.index">
        <p >{{name}}</p>
    </div> -->
  </div>
</template>

<script>
export default {
  name: "Child",
  data() {
    return {};
  },
  props: {
    // name: String,
    // name1: String,
    value: Number,
    onclick: Function,
  },

  methods: {
    onclickchild() {
      this.onclick();
    },
  },
};
</script>

<style scoped>
.child {
  background-color: yellow;
}
</style>