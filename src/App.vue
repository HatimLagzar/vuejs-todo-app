<template>
  <div class="container">
    <h1>Todo App</h1>
    <TodoItem v-for="todo in todoList" :todo="todo" :key="todo.id" />
  </div>
</template>

<script>
import TodoItem from './components/TodoItem.vue'

export default {
  name: 'App',
  components: {
    TodoItem
  },
  data() {
    return {
      todoList: []
    }
  },
  created() {
    this.loadTodoList()
      .then(response => {
        this.todoList = response
      })
  },
  methods: {
    loadTodoList() {
      return fetch('https://jsonplaceholder.typicode.com/todos')
        .then(response => response.json())
        .catch(error => console.log(error))
    }
  }
}
</script>
<style lang="css">
  body {
    font-size: 16px;
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
  }

  .container {
    max-width: 700px;
    margin: 0 auto;
  }
</style>