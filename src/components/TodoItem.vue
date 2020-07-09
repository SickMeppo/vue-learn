<template>
    <li>
       <span>
              <label>
                  <input type="checkbox">
              </label>
              <strong>{{todo.id}}</strong>
              {{todo.title}}
       </span>
        <button class="close-btn">&times</button>
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
        name: "TodoItem"
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

    input {
        margin-right: 1rem;
    }
</style>
