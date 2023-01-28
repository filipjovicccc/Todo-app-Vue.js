<template>
   <div @submit="onSubmit" class="wrapp">
       <h1>Hello from todos</h1>
       <input type="text" placeholder="Add todo here" />
       <button type="submit">Add Todo</button>

   </div>

</template>

<script>
   export default{
    name: "Todos",

    data(){
      return{

          id: Math.floor(Math.random() * 10000),
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
        

     }
    }

   }

</script>

<style>
  .wrapp{
    border: 1px solid black;
    height: 50vh;
  }

</style>