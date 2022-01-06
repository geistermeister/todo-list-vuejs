<template>
  <input type="text" v-model="todo" maxlength="100"/>
  <button @click="onClick({ key: + Date.now(), text: this.todo })">Add ToDo</button>
</template>

<script>
export default {
  name: 'Add',
  data() {
    return {
      todo: ''
    }
  },
  methods: {
    onClick(args) {
      if (this.todo !== '') {
        this.$emit('onAdd', args)
        this.todo = ''
      }
    }
  }
}

</script>

<style scoped>
  input {
    margin-right: 8px;
    height: 40px;
    width: 250px;
    border-radius: 0.25rem;
    border: 1px solid #6f737d;
    outline: none;
  }
  button {
    min-width: 120x;
    height: 40px;
    background: #345fc9;
    color: white;
    border: 1px solid #345fc9;
    border-radius: 0.25rem;
    margin-left: 12px;
    padding: 8px 12px;
    font-weight: 600;
    cursor: pointer;
  }
  button:hover {
    background: #1847ba;
  }
  button:active {
    background: #0332a6;
  }
</style>