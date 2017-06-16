<!-- GRUVBOX THEME -->
<template>
  <div class="hello">
    <h1 :class='msgClass'>{{ msg }}</h1>
    <div v-for='(todo, index) in todos'>
      <p>{{todo}}</p>
      <button @click='deleteTodo(index)'></button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'hello',
  props: {
    todos: {
      type: Array,
      require: true,
    },
    deleteTodo: {
      type: Function,
      require: true,
    },
  },
  data() {
    return {
      msg: 'Cool Stuff',
    };
  },
  computed: {
    msgClass() {
      return this.todos.length ? 'todos' : 'no-todos';
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
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

.todos {
  color: black;
}

.no-todos {
  color: red;
}
</style>
