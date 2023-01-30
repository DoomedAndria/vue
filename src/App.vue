<script >
import ToDo from "./ToDo.vue"
import Comp from "./Comp.vue"
export default{

  components: {ToDo,Comp},

  data: function(){
    return {
      todoList:[
        {
          id:1,
          name: "todo item 1"
        },
        {
          id:2,
          name: "todo item 2"
        },
        {
          id:3,
          name: "todo item 3"
        },
        {
          id:4,
          name: "todo item 4"
        },
      ],

      completedList:[

      ]
    }
  },
  
}
</script>

<template>
  <div class="container">
    <ToDo :items="todoList" :completed="completedList"></ToDo>
    <Comp :items="todoList" :completed="completedList"></Comp>
  </div>
 
</template>

<style scoped>
  .container{
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    font-family: 'Quicksand', sans-serif;
    font-weight: 600;
    background-color: rgba(29, 96, 93, 0.164);
    width: 100vw;
    height: 100vh;
    gap: 20px;
  }

</style>





