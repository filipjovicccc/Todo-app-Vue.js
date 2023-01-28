<template>

<AddTodos @add-todos="addTodos"/>
<Todos @deleteTodos="deleteTodos" :todos="todos"/>
</template>

<script>
import AddTodos from "./components/AddTodos"
import Todos from "./components/Todos.vue"

export default {
  name: 'App',
  components: {
      AddTodos,
      Todos
  },
  data(){
   return{
       
    todos: [],
    
  }
  },
  methods:{
      addTodos(todo){
         
        this.todos = [...this.todos, todo]
       
      },
      deleteTodos(id){
        this.todos = this.todos.filter((todo) => todo.id !== id)
      }
  }
}
</script>

<style>

</style>
