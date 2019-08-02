<template>
  <div id="app">
    <Header />
    <router-view/>
  </div>
</template>


<script>
import Header from './components/layout/Header.vue';
export default {
  name: "app",
  components: {
    Header
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
