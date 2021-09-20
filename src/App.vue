<template>
  <div class="main-container">
    <h1>My task tracker</h1>
    <myTaskTracker />
  </div>
</template>

<script>
import myTaskTracker from './components/myTaskTracker.vue'

export default {
  name: 'App',
  components: {
    myTaskTracker
  }
}
</script>

<style lang="scss" scoped>
@import url('https://fonts.googleapis.com/css2?family=Bebas+Neue&display=swap');

.main-container {
  width: 500px;
  margin-left: auto;
  margin-right: auto;
  background-color: #D8DEF6;
  border-radius: 10px;
  padding-bottom: 10px;
}

h1 {
  text-align: center;
  font-family: 'Bebas Neue', cursive;
}
</style>