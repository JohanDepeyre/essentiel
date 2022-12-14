<template>
    <div>
        <div class="meteo-card weather-animate" :class="[
        { 'weather-rain': meteo.weather[0].main == 'Rain' },
        { 'weather-snow': meteo.weather[0].main == 'Snow' },
        { 'weather-clear': meteo.weather[0].main == 'Clear' || meteo.weather[0].main == 'Mist' },
        { 'weather-clouds': meteo.weather[0].main == 'Clouds' || meteo.weather[0].main == 'Haze' },
        { 'error': getError }]">

            <div class="meteo-card-body">
                <div class="divRonde">
                    <h5 class="meteo-card-title">{{ Math.round(meteo.main.feels_like) + '°' }}</h5>
                </div>

                <div class="weather-icon"
                    :style="[meteo.weather[0].icon ? { 'background-image': 'url(http://openweathermap.org/img/wn/' + meteo.weather[0].icon + '@2x.png)' } : {}]">
                </div>

                <h5>{{ meteo.dt_txt }}</h5>


            </div>
        </div>

    </div>
</template>

<script>


export default {
    name: 'MeteoCard',
    props: {
        meteo: {
            type: Object,
            required: true
        }
    }
}
</script>

<style lang="less" scoped>
.weather-animate {

    width: 100%;
    height: 100vh;
    background-size: cover;
    background-repeat: no-repeat;
    transition: background-image 2s;
    background-size: cover;
    background-position: center;
}

&.weather-default {
    &::after {
        content: "";

        top: 0;
        left: 0;
        width: 100%;
        height: 100vh;
        background-image: linear-gradient(-45deg,
                var(--grayColor),
                var(--darkColor));
    }
}

// clear weather
&.weather-clear {
    background-image: url("../../assets/images/clear.jpg");

    &::after,
    &::before {
        content: "";
        background-image: url("../../assets/images/fog.png");
        height: 100%;

        width: 100%;
        background-repeat: repeat-x;
    }

    &::after {
        top: -50px;
        animation: animateCloud var(--cloudAnimateTime) linear infinite alternate-reverse;
    }

    &::before {
        top: 200px;
        animation: animateCloud calc(var(--clearAnimationTime) / 2) linear infinite alternate;
    }
}

// cloudy weather
&.weather-clouds {
    background-image: url("../../assets/images/clouds.jpg");

    &::after,
    &::before {
        content: "";
        background-image: url("../../assets/images/fog.png");
        height: 100%;
        width: 100%;
        background-repeat: repeat-x;
    }

    &::after {
        top: -50px;
        animation: animateCloud var(--cloudAnimateTime) linear infinite alternate-reverse;
    }

    &::before {
        top: 300px;
        animation: animateCloud calc(var(--cloudAnimateTime) / 2) linear infinite alternate;
    }
}

@keyframes animateCloud {
    0% {
        background-position: -1000px 0;
    }

    100% {
        background-position: 100% 0;
    }
}

// snow weather
&.weather-snow {
    background-image: url("../../assets/images/snow.jpg");

    &::after {
        content: "";
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100vh;
        animation: animateSnow var(--snowAnimateTime) cubic-bezier(0.28, 0.54, 0.47, 0.56) infinite normal;
        background-image: url("../../assets/images/snow2.png"),
            url("../../assets/images/snow3.png"), url("../../assets/images/snow4.png"),
            url("../../assets/images/snow3.png");
    }
}

@keyframes animateSnow {
    0% {
        background-position: 0px 0px, 0px 0px, 0px 0px;
    }

    100% {
        background-position: 400px 1100px, 400px 400px, 600px 600px;
    }
}

// snow weather
&.weather-rain {
    background-image: url("../../assets/images/rain-bg.jpg");

    &::after {
        content: "";
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        background-repeat: repeat;
        animation: animateRain var(--rainAnimateTime) cubic-bezier(0.28, 0.54, 0.47, 0.56) infinite normal;
        background-image: url("../../assets/images/rain-1.png"),
            url("../../assets/images/rain-2.png");
        opacity: 0.8;
    }
}

@keyframes animateRain {
    0% {
        background-position: 0px 0px, 0px 0px, 0px 0px;
    }

    100% {
        background-position: 400px 1100px, 400px 400px, 600px 600px;
    }
}

&.error {
    background-image: url("../../assets/images/error.jpg");
}

/* Définissez les styles pour le composant */
.meteo-card {
    width: 200px;
    height: 300px;
    background-color: #F0F0EF;
    border-radius: 8px;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
    overflow: hidden;
    margin: 15px;

}

.meteo-card-image {
    width: 100%;
    height: 120px;
    object-fit: cover;
}

.meteo-card-body {
    padding: 16px;
    position: relative;
}

.meteo-card-title {
    margin: 0;
    font-size: 16px;
    font-weight: bold;
}

.meteo-card-description {
    margin: 8px 0 0 0;
    font-size: 14px;
    color: #666;
}

.meteo-card-button {
    display: block;
    margin: 16px auto 0 auto;
    padding: 8px 16px;
    background-color: #0097e6;
    color: #fff;
    text-decoration: none;
    border-radius: 4px;
}

.meteo-card-button:hover {
    background-color: #0083c0;
}

.weather-icon {
    background-repeat: no-repeat;
    background-position: center;

    height: 75px;
    width: 75px;
    position: absolute;
    top: 5px;
    left: 25px;
    filter: drop-shadow(1px 1px 0 fade(black, 3)) drop-shadow(-5px -5px 0 fade(black, 8));
}

.divRonde {
    width: 100px;
    height: 100px;
    display: flex;
    align-items: center;
    justify-content: center;
    border-radius: 100%;
    box-shadow: 0 0 40px fade(black, 20);
    background-color: #fff;
    filter: drop-shadow(10px 10px 4px #4444dd);
    margin: auto;
    margin-top: 15px;
}
</style>