<template>
  <div id="app">
    <div class="container">
      <AddTodo/>
      <FilterTodos/>
      <Todos/>
    </div>
    
  </div>
</template>

<script>
import Todos from './components/Todos.vue'
import AddTodo from './components/AddTodo.vue'
import FilterTodos from './components/FilterTodos.vue'
export default {
  name: 'App',
  components: {
    Todos,
    FilterTodos,
    AddTodo,
    
  }
}
</script>

<style>
.container {
    
    width: 100%;
    max-width: 960px;
    padding-right: 15px;
    padding-left: 15px;
    margin-right: auto;
    margin-left: auto;
}
</style>
