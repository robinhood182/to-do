<template>
    <div>
        <p>Completed tasks: {{ todos.filter(todo => todo.done === true).length}}</p>
        <p>Pending tasks: {{ todos.filter(todo => todo.done === false).length}}</p>
        <todo v-for="todo in todos" :key="todo.id" :todo="todo"></todo>
    </div>
</template>

<script type="text/javascript">

import Todo from './Todo';
export default {
    props: ['todos'],
    components: {
        Todo
    }
};
</script>

<style>

</style>
