<template>
    <div>
      <addTodo 
      @add-todo="addTodo"
      />
      <hr/>
        <ul>
            <li
            v-for="(todo, i) in todos"
            :key="i"
            >
                <taskItem 
                :todo="todo"
                v-on:remove-todo="removeTodo"
                :index="i"
                />
            </li>
        </ul>
    </div>
</template>

<script>
import taskItem from './taskItem.vue'
import addTodo from './addTodo.vue'

export default {
  name: 'myTaskTracker',
  components: {
    taskItem, addTodo
  },
  data() {
    return {
      todos: [
        
      ]
    }
  },
  methods: {
    removeTodo(id) {
      this.todos = this.todos.filter(t => t.id !== id)
    },
    addTodo(todo) {
      this.todos.push(todo )
    }
  }
}
</script>

<style lang="scss" scoped>
li {
  margin-bottom: 10px;
  margin-right: 20px;
  border: 1px solid white;
  border-radius: 5px;
}
</style>