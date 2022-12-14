<template>
    <div class="deezer-list">
        <div class="deezer-card">
            <iframe title="deezer-widget" src="https://widget.deezer.com/widget/dark/playlist/1479458365" width="100%"
                height="300" frameborder="0" allowtransparency="true" allow="encrypted-media; clipboard-write"></iframe>
        </div>
        <div class="deezer-card">
            <iframe title="deezer-widget" src="https://widget.deezer.com/widget/dark/playlist/2474689942" width="100%"
                height="300" frameborder="0" allowtransparency="true" allow="encrypted-media; clipboard-write"></iframe>
        </div>
        <div class="deezer-card"><iframe title="deezer-widget"
                src="https://widget.deezer.com/widget/dark/artist/7307/top_tracks" width="100%" height="300"
                frameborder="0" allowtransparency="true" allow="encrypted-media; clipboard-write"></iframe></div>
        <div class="deezer-card">
            <iframe title="deezer-widget" src="https://widget.deezer.com/widget/dark/playlist/9634709682" width="100%"
                height="300" frameborder="0" allowtransparency="true" allow="encrypted-media; clipboard-write"></iframe>
        </div>

    </div>
</template>

<script>

export default {};

</script>
<style>
.deezer-list {
    display: flex;
    flex-wrap: wrap;
    margin-top: 30px;
}

.deezer-card {
    width: 300px;
    background-color: #fff;
    border-radius: 8px;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
    overflow: hidden;
    margin: auto;
    background-color: #191919;
}
</style>