<template>
  <div id="app">
    <form @submit.prevent="addTodo()">
      <label for="newTodo">New Todo</label>
      <input v-model="newTodo" type="text" id="newTodo" />
      <button type="submit">Add Todo</button>
    </form>
    <ul>
      <li v-for="todo in todos" :key="todo">
        {{ todo.title }} 
        <button @click="markDone(todo)">Done</button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      newTodo: "",
      todos: [],
    };
  },
  methods: {
    addTodo() {
      this.todos.push({
        title: this.newTodo,
        done: false
      });
      this.newTodo = "";
    },
    markDone(todo) {
      todo.done = true;
    }
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
ul {
  list-style-type: none;
}
</style>
