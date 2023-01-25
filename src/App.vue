<script setup>
import HorisontalMenu from "./HorisontalMenu.vue"

const listItems = [
                {
                  id: 1,
                  name:"Google",
                  url:"https://www.google.com/",
                  description: "Google LLC is an American multinational technology company focusing on search engine technology, online advertising, cloud computing, computer software, quantum computing, e-commerce, artificial intelligence,[9] and consumer electronics."
                },
                {
                  id: 2,
                  name:"Bing",
                  url:"https://www.bing.com/?toWww=1&redig=8B85287D87334880A26C4E35E8CE5234",
                  description: "Microsoft Bing (commonly known as Bing) is a web search engine owned and operated by Microsoft. The service has its origins in Microsoft's previous search engines: MSN Search, Windows Live Search and later Live Search."
                },
                {
                  id: 3,
                  name:"Yandex",
                  url:"https://yandex.com/",
                  description: "Yandex Search (Russian: Яндекс) is a search engine. It is owned by Yandex, based in Russia. In January 2015, Yandex Search generated 51.2% of all of the search traffic in Russia according to LiveInternet."
                },
                {
                  id: 4,
                  name:"DuckDuckGo",
                  url:"https://duckduckgo.com/",
                  description: "DuckDuckGo (DDG) is an internet search engine that emphasizes protecting searchers' privacy[3] and avoiding the filter bubble of personalized search results"
                },      
              ]

</script>

<template>
  <HorisontalMenu :items="listItems"></HorisontalMenu>
</template>






