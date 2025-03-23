<template>
    <div class="weather-info">
        <div class="icon">
            <img :src="`https://openweathermap.org/img/wn/${$store.state.weatherData.icon}@2x.png`"
                :alt="$store.state.weatherData.icon" class="src">
        </div>
        <div class="temp">{{ kelvinToCelsius($store.state.weatherData.temp) }}&deg</div>
        <div class="text">{{ $store.state.weatherData.text }}</div>
        <div class="location">{{ $store.state.weatherData.city }}, {{ $store.state.weatherData.location }}</div>
    </div>
</template>

<script setup>
function kelvinToCelsius(kelvin) {
    return (kelvin - 273.15).toFixed(1);
}
</script>

<style lang="scss" scoped>
.weather-info {
    padding: 20px;

    &>div {
        margin-bottom: 20px;
        padding: 20px;
        // border: 1px solid #ccc;
    }

    .icon img {
        width: 140px;
    }

    .temp {
        font-size: 4em;
    }

    .text {
        font-size: 2em;
    }
}
</style>