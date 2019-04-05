<template>
  <div id="app">
    <img src="./assets/logo.png">
    <TodoList v-bind:todos="todos"/>
  </div>
</template>

<script>
import TodoList from './components/TodoList'

export default {
  name: 'App',
  components: {
    TodoList
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
