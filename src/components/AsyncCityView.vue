<template>
    <div>

    </div>
</template>

<script setup>
import axios from 'axios'
import { useRoute } from 'vue-router'

const route = useRoute()
const getWeatherData = async() => {
    try {
        const weatherData = await axios.get(`https://api.openweathermap.org/data/3.0/onecall?lat=${route.query.lat}&lon=${route.query.lng}&exclude={part}&appid=52b8e4cef2c3d1a7bcfc969fa41fca22&units=imperial`)
        console.log(weatherData)
    } catch (err) {
        console.log(err)
    }
}

</script>
