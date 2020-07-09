<template>
    <div>
        <h2>Todo application</h2>
        <AddTodo
                @add-todo="addTodo"
        />
        <List
                v-bind:todos="todos"
                @remove-todo="removeTodo"
        />

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
