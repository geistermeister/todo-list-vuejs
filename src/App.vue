<template>
  <div class="container">
    <Header @onAdd="addToDo"/>
    <ToDoList :todos="todos" @onDelete="deleteToDo"/>
  </div>
</template>
    
<script>
  import Header from './components/Header.vue'
  import ToDoList from './components/ToDoList.vue'

  export default {
    name: "App",
    components: {
      Header,
      ToDoList
    },
    data() {
      return {
        todos: []
      }
    },
    methods: {
      addToDo(newToDo) {
        this.todos.push(newToDo)
      },
      deleteToDo(index) {
        this.todos.splice(index, 1)
      }
    }
  }
</script>

<style>
  * {
    box-sizing: border-box !important;
  }
  #app {
    font-family: 'Roboto', sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
    display: flex;
    align-items: center;
    justify-content: center;
  }
  .container {
    width: 400px;
  }
  input {
    -webkit-appearance: none;
    all: unset;
    text-align: left;
    padding: 0 8px;
  }
</style>
