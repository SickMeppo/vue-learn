<template>
    <div class="container">
        <ul class="list">
            <Item
                    v-for="todo of todos"
                    v-bind:todo="todo"
                    v-bind:key="todos.id"
                    v-on:remove-todo="removeTodo"
            />
        </ul>
    </div>
</template>

<script>
    import Item from "./Item";
    export default {
        props: ['todos'],
        name: "List",
        components: {Item},
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
