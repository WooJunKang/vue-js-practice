<template>
  <div id="app">
  <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo"/>
  </div>
</template>

<script>
import Todos from './components/Todos';

export default {
  name: 'App',
  components: {
    Todos
  },
  data( ){
    return {
      todos: [
        {
          id:1,
          title: 'todo one',
          completed: false
        },
        {
          id:2,
          title: 'todo two',
          completed: false
        },
        {
          id:3,
          title: 'todo three',
          completed: false
        }
      ]
    }
  },
  methods: {
    deleteTodo(id){
      // console.log(id)
      this.todos = this.todos.filter(todo => todo.id !== id)
    }
  },
}
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
</style>
