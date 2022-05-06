<script>
export default {
  data() {
    return {
      newTodo: "",
      todos: ["买🍎", "买🍌", "买🍐"],
    };
  },
  methods: {
    addTodo: function () {
      const value = this.newTodo && this.newTodo.trim();
      if (!value) {
        return;
      }
      this.todos.push(value);
      this.newTodo = "";
    },
  },
};
</script>

<template>
  <h1>TODO LIST</h1>
  <div>
    <input v-model="newTodo" @keyup.enter="addTodo" autofocus />
  </div>
  <ul>
    <li v-for="item in todos" :key="item">{{ item }}</li>
  </ul>
</template>

<style scoped>
ul {
  width: 70vw;
  margin: 0 auto;
}
</style>
