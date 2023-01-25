<script>
export default{
    props:{items: Array},

    data(){
        return{
            show: false,
            description:"",
        }
    },
    methods:{
        mouseClick: function(e){
            this.show = true
            let id = e.target.parentNode.id
            let item  = this.items.find(e => e.id == id)
            this.description = item.description            
        },
    }
}
</script>

<template>
    <div class="nav">
        <ul>
            <li v-for="item in items" :key="item.id" :id="item.id" >
                <a :href="item.url" @click.prevent="mouseClick" target="_blank"> {{ item.name }} </a>
            </li>
        </ul>
    </div>
    <div class="desc-cont" v-if="show">
        <p >{{ description }}</p>
    </div>
    
</template>

<style scoped>
.nav{
    background-color: mediumseagreen;
    color: midnightblue;
    display: flex;
    align-items: center;
    gap: 2rem;
    padding: 0.5rem 1rem;
}

.nav ul{
    margin: 0;
    padding: 0;
    list-style: none;
    display: flex;
    gap: 1rem;
}

.nav li{
    padding: 0.5rem;
    border-radius: 20px;
    font-weight: 550;
    font-size: 25px;
    transition: all 0.35s;
}
.nav li:hover{
    background-color: rgba(25, 25, 112, 0.576);
    color: white;
    box-shadow: 0 0 20px 1px #ffffff84;
}

.nav a{
    color: inherit;
    font-weight: inherit;
    font-size: inherit;
    text-decoration: none;
    display: flex;
    align-items: center;
    padding: 0.25rem;
}

.desc-cont{
    width: 40vw;
    padding: 10px;
    margin: 20px 5px;
    background-color: lightcyan;
    border: 2px solid midnightblue;
    border-radius: 10px;
    font-size: 20px;
    color: navy;
    font-weight: 400;
}
</style>