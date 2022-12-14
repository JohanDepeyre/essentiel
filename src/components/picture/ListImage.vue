<template>
    <div class="image-list">
        <ImageNasa msg="App" />
        <ImageJour msg="App" />

    </div>
</template>
<script>

import ImageJour from './ImageJour'
import ImageNasa from './ImageNasa'
export default {
    name: 'ImagesList',
    components: {
        ImageJour,
        ImageNasa
    }
}

</script>
<style>
.image-list {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    padding: 15px;
}
</style>