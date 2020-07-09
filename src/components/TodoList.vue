<template>
    <div>
        <ul class="list">
            <TodoItem/>
        </ul>
    </div>
</template>

<script>
    import TodoItem from "./TodoItem";
    export default {
        name: "TodoList",
        components: {TodoItem},
    }
</script>

<style scoped>
    .list {
        list-style: none;
        padding-left: 0;
    }
</style>
