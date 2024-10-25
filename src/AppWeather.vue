<template>
    <div class="wrapper">
        <h1 class="tittle">Weather aplication</h1>
        <p class="text">Find out the weather in 
            <span class="span">{{ city == '' ? " your city" : city }}</span>
        </p>
        <input type="text" v-model="city" placeholder="enter city">
        <button class="but" v-if="city != ''">Get weather</button>
        <button class="but" v-else="city != ''">your city</button>

    </div>
</template>

<script>
export default {
data() {
    return {
        city: ""
    }
}
}
</script>

<style scoped>
.span {
    font-size: 40px;
}
.but {
    padding: 10px 10px;
    border-radius: 10px;
margin-left: 30px;
cursor: pointer;
font-size: 24px;
}
.but:hover {
    background-color: gold;

}
input {
    width: 300px;
    height: 40px;
border-radius: 10px;
color: white;
background-color: transparent;
border-bottom: 3px solid white;
font-size: 24px;
padding: 5px 20px;
outline: none;
}
input:hover {
    border-bottom: 3px solid gold;
}
.text {
    margin-bottom: 30px;
    font-size: 20px;
}
.tittle {
    font-size: 44px;
margin-top: 20px;
margin-bottom: 10px;
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