<template>
  <div id="app">
    <h1>TODO List</h1>
    <todo-form></todo-form>
    <ul>
      <li v-for="item in todoItems" :key=item.id>
        <todo-item :label=item.label :done=item.done :id=item.id></todo-item>
      </li>
    </ul>
  </div>
</template>

<script>
import TodoItem from './components/TodoItem.vue';
import TodoForm from './components/TodoForm.vue';
import uniqueId from 'lodash.uniqueid';

export default {
  name: 'App',
  components: {
    TodoItem,
    TodoForm,
  },
  data() {
    return {
      todoItems: [
        {
          id: uniqueId("todo-"),
          label: "hello world",
          done: true,
        },
        {
          id: uniqueId("todo-"),
          label: "12 world",
          done: false,
        },
        {
          id: uniqueId("todo-"),
          label: "23 world",
          done: true,
        },
        {
          id: uniqueId("todo-"),
          label: "34 world",
          done: false,
        },
      ]
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
