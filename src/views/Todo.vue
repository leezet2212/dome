<template>
  <div id="todo">
    <form v-on:submit.prevent="addNewTodo">
      <label for="new-todo">Add a todo</label>
      <input v-model="newTodoText" id="new-todo" placeholder="add list todo" />
      <button>Add</button>
    </form>
    <ul>
      <todo-item
        v-for="(todo, index) in todos"
        :key="todo.id"
        :title="todo.title"
        @remove="todos.splice(index, 1)"
      ></todo-item>
    </ul>
  </div>
</template>

<script>
import TodoItem from "../components/TodoList.vue";
export default {
  name: "Todo",
  components: {
    TodoItem,
  },
  data() {
    return {
      newTodoText: "",
      todos: [
        {
          id: 1,
          title: "list todo 1",
        },
        {
          id: 2,
          title: "list todo 2",
        },
        {
          id: 3,
          title: "list todo 3",
        },
      ],
      nextTodoId: 4,
    };
  },
  methods: {
    addNewTodo() {
      this.todos.push({
        id: this.nextTodoId++,
        title: this.newTodoText,
      });
      this.newTodoText = "";
    },
  },
};
</script>

<style>
</style>