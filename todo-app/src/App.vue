<template>
  <div id="app">
    /* v-bind :  used in view to bind and here we are binding our array */
    <todo-list v-bind:todos="todos">

    </todo-list>
    <create-todo v-on:create-todo="createTodo"></create-todo>


  </div>
</template>

<script>
  import TodoList from './components/TodoList';
  import CreateTodo from './components/CreateTodo';
  export default {
    name: 'app',
    components: {
      TodoList,
      CreateTodo,
    },
    data() {
      return {
        /* array one */
        todos: [
          /* each item is an object */
          {
            title: 'Todo A',
            project: 'Project A',
            done: false,
          },
          {
            title: 'Todo B',
            project: 'Project B',
            done: true,
          },
          {
            title: 'Todo C',
            project: 'Project C',
            done: false,
          },
          {
            title: 'Todo D',
            project: 'Project D',
            done: false,
          }],
      };
    },
    methods: {
      createTodo(newTodo) {
        this.todos.push(newTodo);
      },
    },
  };
</script>


<style>
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    color: #2c3e50;
    margin-top: 60px;
  }
</style>

