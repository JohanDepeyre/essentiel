<template>
    <div class="deezer-card text-align-center">

        <p v-if="timeLeft === 0">Joyeux Noël !</p>
        <p v-else>Noël arrive dans {{ timeLeft }}</p>
    </div>
</template>

<script>
export default {
    data() {
        return {
            timeLeft: ""
        }
    },
    created() {
        // Exécuter la fonction countdown toutes les secondes
        setInterval(this.countdown, 1000);
    },
    methods: {
        countdown() {
            // Obtenir la date actuelle
            let now = new Date();

            // Obtenir la date de Noël
            let christmas = new Date(now.getFullYear(), 11, 25);

            // Si Noël est déjà passé cette année, mettre la date de Noël l'année prochaine
            if (now > christmas) {
                christmas.setFullYear(christmas.getFullYear() + 1);
            }

            // Calculer le temps restant en utilisant la méthode .getTime() pour obtenir le nombre de millisecondes écoulées depuis le 1er janvier 1970
            let timeLeft = Math.abs(christmas.getTime() - now.getTime());

            // Convertir le temps restant en jours, heures, minutes et secondes
            let days = Math.floor(timeLeft / (1000 * 60 * 60 * 24));
            let hours = Math.floor((timeLeft % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
            let minutes = Math.floor((timeLeft % (1000 * 60 * 60)) / (1000 * 60));
            let seconds = Math.floor((timeLeft % (1000 * 60)) / 1000);

            // Afficher le temps restant
            this.timeLeft = days + " jours, " + hours + ":" + minutes + ":" + seconds + "";
        }
    }
}
</script>
<style>
.deezer-card {
    width: 80%;
    height: 200px;
    background-color: #ffffff;
    border-radius: 8px;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
    overflow: hidden;
    margin: 15px;
    color: rgb(228, 5, 5);

}
</style>