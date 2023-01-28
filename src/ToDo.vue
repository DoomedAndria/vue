<script>
export default{
    props:{
        items: Array,
        completed: Array
    },

    data:function(){
        return{
            id: this.items.length + 1,
            inptVal: "",
        }
    },

    methods:{

        inptChange:function(e){
            this.inptVal = e.target.value
        },

        addToDo:function(){
            if(this.items.some(c => c.name == this.inptVal)){
                alert("this todo already exists")
            }
            else if(this.inptVal==""){
                alert("todo can't be blank")
            }
            else{
                this.items.push({
                    id: this.id,
                    name: this.inptVal
                })
                this.id++;
            }
            this.$refs["inpt"].value = ""
        },

        inptCheck: function(e){
            let id = e.target.parentNode.getAttribute("item_id") 
            let i  = this.items.indexOf(this.items.find(a => a.id == id)) 
            this.completed.push(this.items.splice(i,1)[0])
        },
    }
}
</script>

<template>
    <div class="todo-cont">
        <h2>To Do List</h2>
        <div>
            <input type="text" @change="inptChange" ref="inpt">
            <button @click="addToDo" >add</button>
        </div>
        
        <ul>
            <li v-for="item in items" :key="item.id" :item_id="item.id">
                <div @click="inptCheck" class="check"><i class="gg-check-r"></i></div> {{ item.name }}
            </li>
        </ul>
    </div>   
</template>

<style scoped>
@import url('https://css.gg/check-r.css');
    .todo-cont{
        display: flex;
        flex-direction: column;
        align-items: center;
        padding: 10px;
        width: 500px;
        height: 85vh;
        gap: 20px;
        background-color: rgb(248, 247, 247);
        color: rgb(78, 78, 78);
        border-radius: 8px;
        box-shadow: rgba(0, 0, 0, 0.24) 0px 3px 8px;
    }
    .todo-cont div{
        display: flex;
        gap: 8px;
        
    }
    h2{
        margin: 0;
    }
    ul{
        width: 100%;
        margin: 0;
        padding: 0;
        list-style-type: none;
        overflow:auto;
        
    }
    li{
        display: flex;
        box-shadow: rgba(0, 0, 0, 0.15) 1.95px 1.95px 2.6px;
        padding: 10px;
        margin: 10px 0;
        font-size: 18px;
        border-radius: 5px;
        background-color: lightgoldenrodyellow;
    }

    input[type=text] {
        width: 400px;
        height: 35px;
        padding: 5px;
        font-size: 20px;
        font-family: 'Quicksand', sans-serif;
        font-weight: 500;
        color: rgb(78, 78, 78);
        outline: none;
        border: none;
        background-color: rgba(211, 211, 211, 0.353);
        border-radius: 5px;
        box-shadow: rgba(0, 0, 0, 0.15) 1.95px 1.95px 2.6px;
    }

    input[type=checkbox]{
        width: 14px;
        height: 14px;
        
    }

    button{
        font-size: 20px;
        padding: 0 10px;
        font-family: 'Quicksand', sans-serif;
        font-weight: 900;
        text-transform: uppercase;
        cursor: pointer;
        border: none;
        background-color: rgba(60, 179, 114, 0.665);
        color: white;
        border-radius: 5px;
        transition: all 0.25s;
    }

    button:hover{
        background-color: rgb(60, 179, 114);
    }
    
    .check{
        margin-right: 10px;
        cursor: pointer;
    }

    i{
        color: mediumseagreen;
        background-color: rgb(217, 243, 229);
    }
</style>