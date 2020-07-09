<template>
    <div class="Todos-container">
        <h2>Todos</h2>
        <router-link class="link" to="/">Home</router-link>
        <AddTodo
                @add-todo="addTodo"
        />
        <List
                v-if="todos.length"
                v-bind:todos="todos"
                @remove-todo="removeTodo"
        />
        <p v-else>No todos!</p>
    </div>
</template>

<script>
    import List from "@/components/List";
    import AddTodo from "@/components/AddTodo";

    export default {
        name: 'App',
        data() {
            return {
                todos: []
            }
        },
        mounted() {
            fetch('https://jsonplaceholder.typicode.com/todos?_limit=3')
                .then(response => response.json())
                .then(json => {
                    this.todos = json
                })
        },
        components: {
            AddTodo,
            List,
        },
        methods: {
            removeTodo(id) {
                this.todos = this.todos.filter(t => t.id !== id)
            },
            addTodo(todo) {
                this.todos.push(todo)
            }
        },
    }
</script>
<style scoped>
    a {
        display: inline-block;
        margin-bottom: 1rem;
    }
    .Todos-container {
        width: 100%;
    }
</style>
