<template>
  <div id="app">
    <img src="./assets/logo.png">
    <TodoList v-bind:todos="todos"/>
    <CreateTodo v-on:add-todo="addTodo"/>
  </div>
</template>

<script>
import TodoList from './components/TodoList'
import CreateTodo from './components/CreateTodo'

export default {
  name: 'App',
  components: {
    TodoList,
    CreateTodo
  },

  methods: {
    addTodo(todo) {
      this.todos.push({
        title: todo.title,
        description: todo.description,
        done: false
      });
    }
  },

  data() {
    return {
      todos: [{
        title: 'Todo A',
        description: 'Description A',
        done: false
      },
      {
        title: 'Todo B',
        description: 'Description B',
        done: true
      },
      {
        title: 'Todo C',
        description: 'Description C',
        done: false
      },
      {
        title: 'Todo D',
        description: 'Description D',
        done: false
      }]
    }
  }
}
</script>

<style>

</style>
