<template>
    <div class="container">
        <ul class="list">
            <TodoItem
                    v-for="todo of todos"
                    v-bind:todo="todo"
                    v-on:remove-todo="removeTodo"
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
        methods: {
            removeTodo(id) {
                this.$emit('remove-todo', id)
            }
        }
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
