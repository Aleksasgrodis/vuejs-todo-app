<template>
  <div id="app">
    <form @submit.prevent="addTodo()">
      <label for="newTodo">New Todo</label>
      <input v-model="newTodo" type="text" id="newTodo" />
      <button type="submit">Add Todo</button>
    </form>
    <h4 v-for="todo in todos" :key="todo"> {{ todo }}</h4>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      newTodo: '',
      todos: [],
    };
  },
  methods: {
    addTodo() {
      this.todos.push(this.newTodo);
      this.newTodo = "";
    },
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
</style>
