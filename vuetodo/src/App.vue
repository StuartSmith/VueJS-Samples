<template>
  <div id="app">
    <!--<img alt="Vue logo" src="./assets/logo.png">-->
    <!--<HelloWorld msg="Welcome to Your Vue.js App"/>-->
    <AddTodo v-on:add-todo="addTodo" class="addtodo" />
    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo" />
  </div>
</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'

import Todos from './components/Todos.vue'
import AddTodo from './components/AddTodo.vue'
import axios from 'axios';

export default {
  name: 'App',
  components: {
      AddTodo,
      Todos
  }, data() {
    return {
      todos: []
    }
  },
    methods: {
    deleteTodo(id) {
      axios.delete(`https://jsonplaceholder.typicode.com/todos/${id}`)
        .then()
        .catch(err => console.log(err));

        this.todos = this.todos.filter(todo => todo.id !== id);
    },
    addTodo(newTodo) {
      const { title, completed } = newTodo;
      axios.post('https://jsonplaceholder.typicode.com/todos', {
        title,
        completed
      })
        .then(res => this.todos = [...this.todos, res.data])
        .catch(err => console.log(err));
    }
  },
   created() {
    axios.get('https://jsonplaceholder.typicode.com/todos?_limit=10')
      .then(res => this.todos = res.data)
      .catch(err => console.log(err));
  }
}
</script>

<style>
* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }
  body {
    font-family: Arial, Helvetica, sans-serif;
    line-height: 1.4;
  }
  .btn {
    display: inline-block;
    border: none;
    background: #555;
    color: #fff;
    padding: 7px 20px;
    cursor: pointer;
  }
  .btn:hover {
    background: #666;
  }
  .addtodo{
    margin-top: 2px;
    margin-bottom: 2px;
    outline: 0;
    border-width: 0 0 2px;
  }

/* Remove the Btn Outline after a button has been clicked on */
.btn:focus {
  outline: none;
  box-shadow: none;
}
</style>
