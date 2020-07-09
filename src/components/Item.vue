<template>
    <li>
       <span v-bind:class="{done: todo.completed}">
              <label>
                  <input type="checkbox"
                         v-on:change="todo.completed = !todo.completed">
              </label>
              <strong>{{todo.id}}</strong>
              {{todo.title}}
       </span>
        <button
                class="close-btn"
                v-on:click="$emit('remove-todo', todo.id)"
        >
            &times
        </button>
    </li>
</template>

<script>
    export default {
        props: {
            todo: {
                type: Object,
                required: true,
            }
        },
        name: "Item"
    }
</script>

<style scoped>
    li {
        display: flex;
        justify-content: space-between;
        padding: .5rem 2rem;
        margin-bottom: 1rem;
        border: 1px solid #ccc;
        border-radius: 5px;
    }

    .close-btn {
        background: red;
        color: white;
        border-radius: 50%;
        font-weight: bold;
        border: none;
    }

    .done {
        text-decoration: line-through;
    }

    input {
        margin-right: 1rem;
    }
</style>
