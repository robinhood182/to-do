<template>
    <div>
        <p class="completed-status">Completed tasks: {{ todos.filter(todo => todo.done === true).length}}</p>
        <p class="completed-status">Pending tasks: {{ todos.filter(todo => todo.done === false).length}}</p>
        <todo v-for="todo in todos" :key="todo.id" :todo.sync="todo" v-on:delete-todo="deleteTodo" v-on:complete-todo="completeTodo"></todo>
    </div>
</template>

<script type="text/javascript">

import Todo from './Todo';
export default {
    props: ['todos'],
    components: {
        Todo
    },
    methods: {
        deleteTodo(todo) {
            const todoIndex = this.todos.indexOf(todo);
            this.todos.splice(todoIndex, 1);
        },
        completeTodo(todo) {
            const todoIndex = this.todos.indexOf(todo);
            if(this.todos[todoIndex].done) {
                return this.todos[todoIndex].done = false;
            }
                this.todos[todoIndex].done = true;
        }
    }
};
</script>

<style>
    .completed-status {
        text-align: center;
    }
</style>
