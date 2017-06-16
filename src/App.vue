<template>
  <div id="app">
    <input v-model='todo'/>
    <button @click='addTodo'>Submit</button>
    <hello 
      :todos="todos"
      :deleteTodo='deleteTodo'
    ></hello>
  </div>
</template>

<script>
import Hello from './components/Hello';

export default {
  name: 'app',
  data() {
    return {
      todo: '',
      todos: [],
    };
  },
  components: {
    Hello,
  },
  methods: {
    addTodo() {
      this.todos = [this.todo, ...this.todos];
      this.todo = '';
    },
    deleteTodo(index) {
      this.todos = this.todos.filter((todo, idx) => idx !== index);
    },
  },
};
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
