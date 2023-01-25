<script setup>
import HorisontalMenu from "./HorisontalMenu.vue"

const listItems = [
                {
                  id: 1,
                  name:"Google",
                  url:"https://www.google.com/"
                },
                {
                  id: 2,
                  name:"Bing",
                  url:"https://www.bing.com/?toWww=1&redig=8B85287D87334880A26C4E35E8CE5234"
                },
                {
                  id: 3,
                  name:"Yandex",
                  url:"https://yandex.com/"
                },      
              ]

</script>

<template>
  <HorisontalMenu :items="listItems"></HorisontalMenu>
</template>






