<template>
    <div>
        <p>Completed tasks: {{ todos.filter(todo => todo.done === true).length}}</p>
        <p>Pending tasks: {{ todos.filter(todo => todo.done === false).length}}</p>
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
            console.log('LOOK HERE', todoIndex);
            console.log('LOOK HERE TOO', this.todos[todoIndex]);
            this.todos[todoIndex].done = true;
        }
    }
};
</script>

<style>

</style>
