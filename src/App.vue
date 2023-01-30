<script >
import Card from './components/Card.vue'
import axios from 'axios'
export default{
  components:{Card},
  data: function(){
    return {
      url: 'https://items.magischer.de/api/products',
      page: 1, 
      limit: 4,
      limits: [4,8,12,16,20],
      lang:"en",
      langs:["en","ge"],
      next: null,
      prev:null,
      first:null,
      last:null,
      dta: []
    }
  },
  methods:{
    getData: function(url = this.url){
      axios.get(url,{
        params:{
          limit: this.limit,
          lang: this.lang
        }
      }).then((response)=>{
      this.dta = response.data.data

      this.page = response.data.current_page

      this.next = response.data.next_page_url
      this.prev = response.data.prev_page_url
      this.first = response.data.first_page_url
      this.last = response.data.last_page_url
      console.log(response.data)
    })
    },
    
  },
  mounted() {
    this.getData()
  },
  
}
</script>

<template>
  <div class="container">
    <div class="cards">
      <Card 
        v-for="item in this.dta"
        :img="item.img.cover"
        :name="item.name"
        :price="item.price"
      >
      </Card>
    </div>
    <div class="conf">
      <div>
        <button :disabled="this.first?false:true" @click="getData(this.first)">&lt;&lt;</button>
        <button :disabled="this.prev?false:true" @click="getData(this.prev)">&lt;</button>
        <button :disabled="this.next?false:true" @click="getData(this.next)">&gt;</button>
        <button :disabled="this.last?false:true" @click="getData(this.last)">&gt;&gt;</button>
      </div>

      <br>

      <p>item limit</p>
      <select v-model="limit" @change="getData()">
        <option v-for="l in limits" >{{l}}</option>
      </select>

      <br>

      <p>language</p>
      <select v-model="lang" @change="getData()">
        <option v-for="l in langs" >{{l}}</option>
      </select>

      <h1>PAGE: {{this.page}}</h1>
    </div>
  </div>
 
</template>

<style scoped>

  .container{
    display: flex;
    flex-direction: row;
   
    font-family: 'Quicksand', sans-serif;
    font-weight: 600;
    background-color: rgba(29, 96, 93, 0.062);
    min-width: 100vw;
    min-height: 100vh;
  }

  .cards{
    width: 80%;
    padding: 10px;
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
  }

  .conf{
    display: flex;
    flex-direction: column;
    color: rgba(0, 0, 255, 0.679);
  }

  .conf select{
    outline: none;
    border: none;
    height: 30px;
    background-color: rgba(211, 211, 211, 0.55);
    border-radius: 5px;
    font-family: 'Quicksand', sans-serif;
    font-weight: 900;
    color: darkslategrey;
    box-shadow: rgba(0, 0, 0, 0.24) 0px 3px 8px;
    cursor: pointer;
  }

  .conf div{
    padding-top: 50px;
    display: flex;
    gap: 5px;
  }
 
  .conf button{
    font-size: 16px;
    padding: 10px 10px;
    font-family: 'Quicksand', sans-serif;
    font-weight: 900;
    text-transform: uppercase;
    cursor: pointer;
    border: none;
    background-color: rgba(32, 178, 171, 0.613);
    color: white;
    border-radius: 5px;
    transition: all 0.25s;
  }

  .conf button:hover{
    background-color: lightseagreen;
  }

  .conf button:disabled{
    background-color: lightgray;
  }

</style>





