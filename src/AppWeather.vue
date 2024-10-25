<template>
<div class="wrapper">
<h1 class="tittle">Weather aplication</h1>
<p class="text">find out the weather in your city</p>
<input type="text" name="" placeholder="enter city">
<button>Get weather</button>
</div>
</template>

<script>
export default {

}
</script>

<style scoped>
input {
    width: 300px;
    height: 40px;
border-radius: 10px;
color: white;
background-color: transparent;
border-bottom: 3px solid gold;
font-size: 24px;
padding: 5px 8px;
outline: none;

}
.text {
    margin-bottom: 30px;
}
.tittle {
margin-top: 50px;
margin-bottom: 30px;
}
.wrapper {
    width: 900px;
    height: 500px;
    border-radius: 50px;
    border: 2px solid white;
    padding: 20px;
    text-align: center;
}

</style>