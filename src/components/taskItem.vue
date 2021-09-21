<template>
    <div>
        <span v-bind:class="{done: todo.completed}">
            <input type="checkbox" v-model="todo.completed">{{ index + 1 }}
            {{ todo.title }}
        </span>
        <button class="btn" v-on:click="$emit('remove-todo', todo.id)">&times;</button>
    </div>
</template>

<script>
export default {
    props: {
        todo: {
            type: Object,
            required: true
        },
        index: Number
    }
}
</script>

<style lang="scss" scoped>
@import url('https://fonts.googleapis.com/css2?family=PT+Sans&display=swap');

span {
    font-family: 'PT Sans', sans-serif;
}

div {
    display: flex;
    justify-content: space-between;
    padding: 5px 10px;
    background-color: white;
}

input {
    margin-right: 10px;
}

.btn {
    border-radius: 50%;
    font-weight: bold;
}

.done {
    text-decoration: line-through;
}
</style>