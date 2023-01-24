<script>
export default{
    props:{items: Array}
}
</script>

<template>
    <div class="nav">
        <ul>
            <li v-for="item in items">  <a href="#">{{ item }}</a> </li>
        </ul>
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
    font-weight: 450;
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
</style>