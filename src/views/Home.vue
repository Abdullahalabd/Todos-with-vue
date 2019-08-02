<template>
  <div id="app">
    <!-- <Header /> -->
    <AddTodo v-on:addTodo="addTodo"/>
    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo" />
  </div>
</template>

<script>
import HelloWorld from '../components/HelloWorld.vue';
import Todos from '../components/Todos.vue';
// import Header from '../components/Header.vue';
import AddTodo from '../components/AddTodo.vue';
import axios from 'axios';

export default {
  name: 'Home',
  components: {
    HelloWorld,
    Todos,
    // Header,
    AddTodo
  },
  data() {
    return {
      todos: []
    };
  },

  methods:{
    deleteTodo(id) {
      axios.delete("https://jsonplaceholder.typicode.com/todos/"+id)
      .then(res => this.todos = this.todos.filter((t) => t.id !== id))
      .catch(e => console.log(e));
    },
    addTodo(todo) {
      const {title, completed} = todo;
      axios.post("https://jsonplaceholder.typicode.com/todos", {title, completed})
      .then(res => this.todos.push(res.data))
      .catch(e => console.log(e));
    }
  },

  created() {
    console.log("created");
    axios.get("https://jsonplaceholder.typicode.com/todos?_limit=5")
    .then(res => this.todos = res.data)
    .catch( e => console.log(e));
  }
}
</script>

<style>
  * {
    margin: 0px;
    padding: 0px;
    box-sizing: border-box;
  }
  body{
    font-family: Arial, Helvetica, sans-serif;
    line-height: 1.4;
  }
  .btn{
    display: inline-block;
    border: none;
    background: #555;
    color: white;
    padding: 7px 20px;
    cursor: pointer;
  }
  .btn:hover{
    background: #666;
  }
</style>
