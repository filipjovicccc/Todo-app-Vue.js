<template>
    <div :key="todo.id" v-for="todo in todos">
       <h1>Hello From Todos</h1>
        <p>{{todo.text}}</p>
        <button @click="onClick(todo)">Delete Todo</button>
    </div>

</template>

<script>
  export default{
       
    name: "Todos",
    props: {
        todos: Array
    },
    methods:{
        onClick(todo){
           this.$emit("deleteTodos", todo.id)
        }
    },
    emits: ["deleteTodos"]
  }

</script>

<style>

</style>