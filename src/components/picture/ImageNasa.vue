
<template>
    <div class="divImage">
        <img class="wImage" v-bind:src="image" alt="image aléatoire de nasa" />

    </div>
</template>

<script>
// dans votre composant VueJS
import axios from 'axios';

export default {
    name: 'ImageNasa',
    data() {
        return {
            titre: null,
            image: null,
        };
    },
    created() {
        axios.get('https://api.nasa.gov/planetary/apod?api_key=V5AvP4sOzPmVIPEfhwgj7lIzcGErCS6kbjhBeJcH')
            .then((response) => {
                console.log(response.data)
                // mettre à jour les données du composant avec les données de l'API
                let resultat = response.data;
                this.titre = resultat.title;
                this.image = resultat.url;
            });
    },
};

</script>
<style>
.divImage {
    width: 30%;
}

.wImage {
    width: 100%;
}
</style>
