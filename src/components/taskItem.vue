<template>
  <div>
    <div class="edit-group" v-if="!toEdit">
      {{ index + 1 }})
      <input type="checkbox" class="checkbox" v-model="todo.completed" />
      <span
        v-bind:class="{ done: todo.completed }"
        v-on:click="toEdit = !toEdit"
      >
        {{ todo.title }}
      </span>
    </div>

    <div v-if="toEdit">
      <input type="text" v-model="titleField" />
      <div class="btn-container">
        <button v-on:click="(todo.title = titleField), (toEdit = false)">
          Edit
        </button>
      </div>
    </div>
    <div class="btn-container">
      <button class="btn" v-on:click="$emit('remove-todo', todo.id)">
        &times;
      </button>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    todo: {
      type: Object,
      required: true,
    },
    index: Number,
  },
  data() {
    return {
      toEdit: false,
      titleField: this.todo.title,
    };
  },
};
</script>

<style lang="scss" scoped>
@import url("https://fonts.googleapis.com/css2?family=PT+Sans&display=swap");

span {
  cursor: pointer;
}

span {
  font-family: "PT Sans", sans-serif;
  word-break: break-all;
  margin-bottom: 4px;
}

div {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 5px 10px;
  background-color: white;
}

input {
  margin-right: 10px;
}

.checkbox {
  cursor: pointer;
}

.btn {
  border-radius: 50%;
  font-weight: bold;
}

.done {
  text-decoration: line-through;
}

.btn-container {
  height: 20px;
}
</style>