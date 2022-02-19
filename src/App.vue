<template>
  <div id="app">
    <h1>组件化todolist</h1>
     <TodoList></TodoList>  
    <!-- <ParentSlot></ParentSlot> -->
  </div>
</template>

<script>
import Vue from "vue"
import TodoList from "./components/TodoList.vue"
import Button from "./components/TodoButton.vue"
// import ParentSlot from './components/testSlot/ParentSlot.vue'
Vue.component(Button.name,Button)
export default{
  name:"App",
  components:{
    TodoList,
    // ParentSlot
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
