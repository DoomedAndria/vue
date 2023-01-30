<script>
export default{
    props:{
        img:String,
        name:String,
        price:Number,
    }
}

</script>

<template>
    <div class="card">
        <div class="img">
            <img :src="img">
        </div>
        <div class="name">
            {{ this.name }}
        </div>
        <div class="price">
            {{ this.price }} ₾
            <button class="cart">Add <i class="gg-shopping-cart"></i></button>
        </div>
    </div>
</template>

<style scoped>
@import url('https://css.gg/shopping-cart.css');
    .card{
        width: 250px;
        height: 300px;
        margin: 10px;
        padding: 10px;
        border-radius: 10px;
        box-shadow: rgba(0, 0, 0, 0.15) 1.95px 1.95px 2.6px;
        background-color: rgba(108, 206, 152, 0.421);
        color: darkslategrey;
        text-align: center;
        
    }
    .img{
        height: 170px;
        width: 100%;
    }

    .img img{
        object-fit: cover;
        width: 100%;
        height: 100%;
        border-radius: 7px;
        box-shadow: rgba(0, 0, 0, 0.15) 1.95px 1.95px 2.6px;
    }
    .name{
        display: flex;
        align-items: center;
        justify-content: center;
        width: 100%;
        height: 80px;
        font-size: 22px;
    }
    .price{
        display: flex;
        justify-content: center;
        align-items: center;
        gap: 30px;
        font-size: 18px;
        color: rgba(220, 20, 60, 0.791);
    }
    .cart{
        display: flex;
        gap: 5px;
        font-size: 16px;
        padding: 10px 10px;
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

    .cart:hover{
        background-color: rgb(60, 179, 114);
    }
</style>