<template>
  <div class="todo_container">
    <div v-for="(todo, index) in todos" :key=todo.key>
      <ToDo :todo="todo" :index="index"/>
    </div>
  </div>
</template>

<script>
  import ToDo from './ToDo.vue'
  export default {
    props: {
      todos: Array,
      onDelete: Function
    },
    components: {
      ToDo
    }
  }
</script>

<style scoped>
  .todo_container {
    display: flex;
    padding: 12px 0;
    flex-direction: column;
  }
  .todo_container div:not(:last-of-type) {
    margin-bottom: 8px;
  }
</style>