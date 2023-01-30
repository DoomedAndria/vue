<script>
export default{
    props:{
        items: Array,
        completed: Array
    },
    data:function(){
        return{
           
        }
    },
    methods:{
        deleteCompItem:function(e){
            let id = e.target.parentNode.parentNode.getAttribute("item_id")
            let i = this.completed.indexOf(this.completed.find(c => c.id == id))
            this.completed.splice(i,1)
        },
        undoComp: function(e){
            let id = e.target.parentNode.parentNode.parentNode.getAttribute("item_id")
            let i = this.completed.indexOf(this.completed.find(c => c.id == id))
            this.items.push(this.completed.splice(i,1)[0])
        }
    }

}

</script>

<template>
    <div class="comp-cont">
        <h2>Completed List</h2>
        
        <ul>
            <li v-for="item in completed" :key="item.id" :item_id="item.id">
                {{ item.name }}
                <div class="bts">
                    <div @click="undoComp">
                        <i class="gg-undo"></i>               
                    </div>
                    <div @click="deleteCompItem">
                        <i class="gg-trash"></i>
                    </div>
                </div>    
            </li>
        </ul>
    </div>
</template>

<style scoped>
@import url('https://css.gg/trash.css');
@import url('https://css.gg/undo.css');
.comp-cont{
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
    color: rgb(55, 191, 116);
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
    justify-content: space-between;
    box-shadow: rgba(0, 0, 0, 0.15) 1.95px 1.95px 2.6px;
    padding: 10px 20px 10px 10px ;
    margin: 10px 0;
    font-size: 18px;
    border-radius: 5px;
    background-color: rgba(60, 179, 114, 0.207);
}
i{
    cursor: pointer;
}
.gg-trash{
    color: crimson;
}

.gg-undo{
    margin-top: 3px;
    color: orangered;
}
.bts{
    padding: 5px;
    display: flex;
    gap: 20px;
}

</style>
