<template>
    <div>
        <h1>Liste de meteo</h1>
        <div class="meteo-list">
            <meteo-card v-for="meteo in meteos" :key="meteo.dt" :meteo="meteo" />
        </div>

    </div>
</template>

<script>
import axios from 'axios'
import MeteoCard from './MeteoCard'
import dayjs from 'dayjs'
export default {
    name: 'MeteoList',
    components: {
        MeteoCard
    },
    data() {
        return {
            meteos: []
        }
    },
    created() {
        // Récupérez les recettes à partir de l'API
        axios.get('http://api.openweathermap.org/data/2.5/forecast?lat=45.5031824&lon=-73.5698065&cnt=18&units=metric&appid=9622b47b8c311484f5722e3d63812036')
            .then(response => {
                const result = []
                let dataArray = response.data
                for (let i = 0; i < dataArray.list.length; i += 2) {
                    dataArray.list[i].dt_txt = dayjs(dataArray.list[i].dt_txt).format('dddd,  D MMMM, YYYY h:mm A')
                    result.push(dataArray.list[i]);
                }

                this.meteos = result

            })
            .catch(error => {
                // Gérez les erreurs ici
                console.error(error)
            })
    }
}
</script>

<style>
/* Définissez les styles pour le composant */
.meteo-list {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    padding: 15px;
}
</style>