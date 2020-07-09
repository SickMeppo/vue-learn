<template>
    <div class="container">
        <ul class="list">
            <TodoItem
                    v-for="todo of todos"
                    v-bind:todo="todo"
            />
        </ul>
    </div>
</template>

<script>
    import TodoItem from "./TodoItem";
    export default {
        props: ['todos'],
        name: "TodoList",
        components: {TodoItem},
    }
</script>

<style scoped>
    .list {
        list-style: none;
        margin: 0;
        padding: 0;
    }
    .container {
        width: 100%;
    }
</style>
