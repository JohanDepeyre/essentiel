<template>
    <div class="deezer-list">

        <SantaCard msg="App" />

        <div class="deezer-card">
            <iframe title="deezer-widget"
                src="https://widget.deezer.com/widget/dark/playlist/2474689942?tracklist=false" width="100%"
                height="100%" frameborder="0" allowtransparency="true"
                allow="encrypted-media; clipboard-write"></iframe>
        </div>

        <ChristmasCard msg="App" />



    </div>
</template>

<script>
import ChristmasCard from './ChristmasCard'
import SantaCard from './SantaCard'
export default {
    name: 'DeezerCard',
    components: {

        ChristmasCard,
        SantaCard
    }


};

</script>
<style>
.deezer-list {
    display: flex;
    flex-wrap: wrap;
    padding: 15px;

}

.deezer-card {
    width: 100%;
    height: 200px;
    background-color: #F0F0EF;
    border-radius: 8px;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
    overflow: hidden;
    margin: 15px;

}
</style>