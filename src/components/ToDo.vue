<template>
  <div>
    <span :title="todo.text">{{todo.text}}</span>
    <span class="material-icons" title="Click to delete the entry" @click="deleteToDo(index)">delete</span>
  </div>
</template>

<script>
  export default {
    props: {
      todo: Object,
      index: Number
    },
    methods: {
      deleteToDo(index) {
        this.$parent.$emit('onDelete', index)
      }
    }
  }
</script>

<style scoped>
  div {
    display: flex;
    align-items: center;
    background: #f5f5f5;
    width: 100%;
    height: 50px;
    padding: 8px 12px;
    border-radius: 0.25rem;
  }
  span:first-of-type {
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: nowrap;
    margin-right: 8px;
  }
  .material-icons {
    cursor: pointer;
    user-select: none;
    margin-left: auto;
    color: #dedede;
  }
  .material-icons:hover {
    color: #6f737d;
  }
</style>