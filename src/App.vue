<template>
  <div id="app">
    <Todos v-bind:todos="todos" />
  </div>
</template>

<script>
import Todos from './components/Todos';
export default {
  name: 'App',
  components: {
    Todos
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
