<template>
  <div id="todolist">
    <li>
      {{ title }}
      <button @click="$emit('remove')">Remove</button>
    </li>
  </div>
</template>

<script>
export default {
  name: "Todolist",
  props: {
    title: Array,
  },
  emits: ["remove"],
};
</script>

<style>
</style>