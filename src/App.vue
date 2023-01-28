<script >
 import List from "./List.vue"
export default{

  components: {List},

  data: function(){
    return {
      todoList:[
        {
          id:2,
          name: "todo item 2"
        },
        {
          id:3,
          name: "todo item 3"
        }
      ],

      completedList:[
        
      ]
    }
  }
}
</script>

<template>
  <List :items="todoList"></List>
</template>

<style scoped>


</style>





