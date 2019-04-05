<template>
  <div id="app">
    <img src="https://media0.giphy.com/media/J7jsbfcJ2O5eo/giphy.webp?cid=790b76115ca7b7da4a36387963ae49fc">
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
  img {
   display: block;
  margin-left: auto;
  margin-right: auto;
  width: 40%;
  }
</style>
