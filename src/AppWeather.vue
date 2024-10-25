<template>
    <div class="wrapper">
        <h1 class="tittle">Weather Application</h1>
        <p class="text">Find out the weather in
            <span class="span">{{ city == '' ? "your city" : city }}</span>
        </p>
        <input type="text" v-model="city" placeholder="Enter city">
        <button class="but" @click="getWeather()" v-if="city.trim() !== ''">Get weather</button>
        <button class="but" disabled v-else>Enter city</button>
        <p class="text">{{ error }}</p>
        <p class="tet" v-if="info && info.main">Температура: <span class="spa">{{ Math.round(info.main.temp) }}°C</span></p>
        <p class="tet" v-if="info && info.main">Ощущается как: <span class="spa">{{ Math.round(info.main.feels_like) }}°C</span></p>
        <p class="tet" v-if="info && info.main">Влажность: <span class="spa">{{ info.main.humidity }}%</span></p>
        <p class="tet" v-if="info && info.wind">Скорость ветра: <span class="spa">{{ info.wind.speed }} м/с</span></p>
        <p class="tet" v-if="info && info.weather">Описание: <span class="spa">{{ info.weather[0].description }}</span></p>
    </div>
</template>

<script>
import axios from 'axios';

export default {
    data() {
        return {
            city: '',
            error: '',
            info: null
        }
    },
    computed: {
        cityName() {
            return this.city;
        }
    },
    methods: {
        getWeather() {
            if (this.city.trim().length < 2) {
                this.error = 'Введите более 1 символа';
                return false;
            }

            this.error = '';
            axios.get(`https://api.openweathermap.org/data/2.5/weather?q=${this.city}&units=metric&appid=581f2fd2d7c7cd7fdada18bd7ec0b718`)
                .then(res => {
                    this.info = res.data;
                    this.error = '';
                })
                .catch(err => {
                    this.error = 'Не удалось получить данные о погоде. Пожалуйста, проверьте правильность ввода города.';
                    this.info = null;
                });
        }
    }
}
</script>

<style scoped>
.spa {
    margin-left: 40px;
}
.tet {
    font-size: 40px;
    color: white;
}

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
    border-radius: 20px;
    border: 2px solid white;
    padding: 20px;
    text-align: center;
    background-color: rgba(0, 0, 0, 0.5);
}
</style>
