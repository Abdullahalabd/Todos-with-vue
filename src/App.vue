<template>
  <div id="app">
    <Header />
    <AddTodo v-on:addTodo="addTodo"/>
    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo" />
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue';
import Todos from './components/Todos.vue';
import Header from './components/layout/Header.vue';
import AddTodo from './components/AddTodo.vue';

export default {
  name: 'app',
  components: {
    HelloWorld,
    Todos,
    Header,
    AddTodo
  },
  data() {
    return {
      todos: [
        {
          id: 1,
          title: "First todo",
          completed: false
        },
        {
          id: 2,
          title: "Second todo",
          completed: false
        },
        {
          id: 3,
          title: "Third todo",
          completed: false
        }
        
      ]
    };
  },

  methods:{
    deleteTodo(id) {
      this.todos = this.todos.filter((t) => t.id !== id);
    },
    addTodo(todo) {
      this.todos.push(todo);
    }
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
