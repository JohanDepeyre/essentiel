Import { createClient } from 'pexels';



<template>
    <div class="divImage">
        <img class="wImage" v-bind:src="image" alt="image aléatoire de nature" />

    </div>
</template>

<script>
// dans votre composant VueJS
import axios from 'axios'

export default {
    name: 'ImageJour',
    data() {
        return {
            image: null,
        };
    },
    created() {
        axios.get('https://api.pexels.com/v1/search?per_page=1&query=Nature', {
            headers: {
                'Authorization': '563492ad6f917000010000017556f377b34643c4808de362dea3c35e'
            }
        }).then((response) => {
            this.image = response.data.photos[0].src.large2x;
        });


    }
};

</script>
<style>
.divImage {
    width: 50%;
}

.wImage {
    width: 100%;
}
</style>
