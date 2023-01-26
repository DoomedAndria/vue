<script >
export default{
  data(){
    return{
      width:null,
      height:null,
      color:null
    }
  },
  computed:{
    computeArea(){
      return this.width * this.height
    }
  }
}

</script>

<template>
  <div class="container">
    <div class="inpt">

      <label >Width (px)</label><br/>
      <input  v-model="width" type="text"><br/>
      <br/>
      <label >Height (px)</label><br/>
      <input  v-model="height" type="text"><br/>
      <br/>
      <label >color</label><br/>
      <input  v-model="color" type="color"><br/>

      <p>Area: {{computeArea}}</p>

    </div>

    <div v-bind:style="{ width: width + 'px',height: height + 'px' ,backgroundColor:color}" class="default">

    </div>
  </div>
  
  

</template>

<style scoped>

.container{
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
}
.default{
  margin: 30px;
  width: 300px;
  height: 300px;
  background-color: lightseagreen;
  border: 2px solid black;
}
.inpt{
  padding: 20px;
}

</style>





