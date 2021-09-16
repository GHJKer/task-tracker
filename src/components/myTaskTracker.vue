<template>
    <div>
        <ul>
            <li
            v-for="(todo, index) in todos"
            :key="index"
            >
                <taskItem 
                :todos="todos"
                />
            </li>
        </ul>
    </div>
</template>

<script>
import taskItem from './taskItem.vue'

export default {
  name: 'myTaskTracker',
  components: {
    taskItem
  },
  data() {
    return {
      todos: [
        {id: 1, title: 'Написать базовую структуру приложения', completed: false},
        {id: 2, title: 'Создать данные в поле "данные"', completed: false},
        {id: 3, title: 'Наслаждаться созданным приложением', completed: false}
      ]
    }
  }
}
</script>