<template>
  <div id="app">
    <Header />
    <AddTodo v-on:a-todo="AddTodoIn" />

    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo"/>
  </div>
</template>

<script>
import Header from './components/Header'
import Todos from './components/Todos';
import AddTodo from './components/AddTodo'
export default {
  name: 'App',
  components: {
    Todos,
    Header,
    AddTodo
  },
  data() {
    return {
      todos: [
        {
          id: 1,
          task: "First Todo Item",
          completed: true

        },
        {
          id: 2,
          task: "Second Todo Item",
          completed: false

        },
        {
          id: 3,
          task: "third Todo Item",
          completed: true

        }
      ]
    }
  },
  methods: {
    deleteTodo(id) {
      this.todos = this.todos.filter(todo => (todo.id != id))
    },
    AddTodoIn(newTodo) {
      this.todos = [...this.todos, newTodo]
    }
  }
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;

}
body {
  font-family:Arial, Helvetica, sans-serif;
}
</style>
