<template>
   <form @submit="onSubmit" class="wrapp">
       <h1>Hello from Add todos</h1>
       <input v-model="text" name="text" type="text" placeholder="Add todo here" />
       <button type="submit">Add Todo</button>

   </form>

</template>

<script>
   export default{
    name: "AddTodos",

    data(){
      return{
         text: "",
      }  
    },
    methods:{
     onSubmit(e) {
         e.preventDefault()

         if(!this.text){
                alert("Please add a task")
                return
            }

      const newTodos ={
        id: Math.floor(Math.random() * 10000),
        text: this.text
      }
         
    
      this.$emit("add-todos", newTodos),
      this.text = ''
    
    }  
  },

   }

</script>

<style>
  .wrapp{
    border: 1px solid black;
    height: 50vh;
  }

</style>