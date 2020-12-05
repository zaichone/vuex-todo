<template>
  <div>
      <h1>Todos</h1>
      <div class="todos">
          <div v-for="todo in allTodos" :key="todo.id" class="todo">
              <h3>{{todo.title}}</h3>
              <font-awesome-icon :icon="['fas', 'trash']" @click="deleteTodo(todo.id)"/>
          </div>
      </div>
  </div>
</template>

<script>
import {mapGetters, mapActions} from 'vuex';
import { library } from '@fortawesome/fontawesome-svg-core'
import { faTrash } from '@fortawesome/free-solid-svg-icons'
 
library.add(faTrash)
export default {
    name:"Todos",
    methods:{
        ...mapActions(["fetchTodos", "deleteTodo"])
    },
    computed: mapGetters(['allTodos']),
    created(){
        this.fetchTodos();
    }
}
</script>

<style scoped>
    .todos{ display:grid; grid-template-columns:repeat(3, 1fr); grid-gap:1rem; }
    .todo{ background:aqua; padding:10px; color:#eee; position:relative; }
    .todo svg{ position:absolute; bottom:10px; right:10px; }
</style>