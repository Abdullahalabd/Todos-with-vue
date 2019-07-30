<template>
  <div id="app">
    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo" />
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Todos from './components/Todos.vue'
export default {
  name: 'app',
  components: {
    HelloWorld,
    Todos
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
</style>
