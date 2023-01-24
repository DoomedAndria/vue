<template>
    <li class="listItem">
        {{ title }}
        <button>delete</button>
    </li>
</template>

<script>
export default{
    data(){
        
    },
    props:{
        title: String
    }
}
</script>

<style scoped>
.listItem{
    color: mediumseagreen;
    font-weight: 900;
    text-transform: uppercase;
}
</style>