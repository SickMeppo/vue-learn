<template>
    <form @submit.prevent="onSubmit">
        <label>
            <input type="text" v-model="title">
            <button type="submit">Create</button>
        </label>
    </form>
</template>

<script>
    export default {
        name: "AddTodo",
        data() {
            return {
                title: ''
            }
        },
        methods: {
            onSubmit() {
                console.log('sumbit', this.title)
                if (this.title.trim()) {
                    const newTodo = {
                        id: Date.now(),
                        title: this.title,
                        completed: false
                    }
                    this.$emit('add-todo', newTodo)
                    this.title = ''
                }
            }
        }
    }
</script>

<style scoped>
    form {
        display: flex;
        margin-bottom: 20px;
    }

    input {
        border: 1px solid #ccc;
        border-radius: 5px;
        padding: .10rem .5rem;
    }

    button {
        margin-left: 10px;
        border: 1px solid #ccc;
        background: white;
        color: black;
        font-weight: bold;
        border-radius: 5px;
        padding: .10rem .5rem;
    }
</style>
