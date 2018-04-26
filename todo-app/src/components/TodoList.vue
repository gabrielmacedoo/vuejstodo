<template>
  <div>
    <!-- filter out the ones with true value and return them || true as complete -->
    <p> Completed Tasks: {{ todos.filter(todo => {return todo.done === true}).length }}</p>
    <!-- filter out the ones with false value and return them || false as not complete -->
    <p> Pending Tasks: {{ todos.filter(todo => {return todo.done === false}).length }}</p>
    <!-- create a card for each todo item using vue loop -->

    <todo v-on:delete-todo="deleteTodo" v-on:complete-todo="completeTodo" v-for="todo in todos"  :todo.sync="todo">

    </todo>
  </div>
</template>
<script type="text/javascript">
  import Todo from './Todo';
  export default {
    props: ['todos'],
    components: {
      Todo,
    },
    methods: {
      deleteTodo(todo) {
        const todoIndex = this.todos.indexOf(todo);
        this.todos.splice(todoIndex, 1);
      },
      completeTodo(todo){
        const todoIndex = this.todos.indexOf(todo);
        this.todos[todoIndex].done = true;
      },
    },
  };
</script>

