<template>
    <div id="app">
        <h1>Todo application</h1>
        <AddTodo
                @add-todo=""
        />
        <List
          v-bind:todos="todos"
          @remove-todo="removeTodo"
        />

    </div>
</template>

<script>
    import List from "./components/List";
    import AddTodo from "./components/AddTodo";

    export default {
        name: 'App',
        data() {
            return {
                todos: [
                  {id: 1, title: 'Buy car', completed: false},
                  {id: 2, title: 'Buy bear', completed: false},
                  {id: 3, title: 'Buy joke', completed: false},
                ]
            }
        },
        components: {
            AddTodo,
            List,
        },
        methods: {
           removeTodo(id) {
               this.todos = this.todos.filter(t => t.id !==id)
           }
        },
    }
</script>

<style>
    #app {
        font-family: Avenir, Helvetica, Arial, sans-serif;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
        text-align: center;
        color: #2c3e50;
        margin-left: auto;
        margin-right: auto;
        width: 800px;
        height: 100vh;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-content: center;
        align-items: center;
    }
</style>
