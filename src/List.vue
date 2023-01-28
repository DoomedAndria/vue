<script>
export default{
    props:{items: Array},

    data:function(){
        return{
            id: this.items.length + 1,
            inptVal: "",
            chekedIds:[]
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
            if(e.target.checked){
                this.chekedIds.push(id)
            }
            else{
                let i  = this.chekedIds.indexOf(id)
                this.chekedIds.splice(i,1)
            }
            
            console.log(this.chekedIds)
        },

        deleteChecked: function(){
            this.chekedIds.forEach(c =>{
                let i = this.items.indexOf(this.items.find(d=> d.id == c))
                this.items.splice(i,1)
            })

            this.chekedIds = []
        },
    }
}
</script>

<template>
    <input type="text" @change="inptChange" ref="inpt"><button @click="addToDo" >add</button>
    <ul>
        <li v-for="item in items" :key="item.id" :item_id="item.id">
            <input type="checkbox" @change="inptCheck"> {{ item.name }}
        </li>
    </ul>

    <button v-if="chekedIds.length > 0" @click="deleteChecked">delete checked items</button>
</template>