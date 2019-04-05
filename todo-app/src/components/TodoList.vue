<template>
    <div>
        <p>Completed tasks: {{ todos.filter(todo => todo.done === true).length}}</p>
        <p>Pending tasks: {{ todos.filter(todo => todo.done === false).length}}</p>
        <todo v-for="todo in todos" :key="todo.id" :todo="todo" v-on:delete-todo="deleteTodo"></todo>
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
        }
    }
};
</script>

<style>

</style>
