<template>
    <div class="santa-card">
        <img id="imageSanta" src="../../assets/images/santa.gif" alt="pere noel" />

    </div>
</template>

<script>
export default {

};
</script>
<style>
.santa-card {
    width: 100%;
    height: 200px;
    background-color: #ffffff;
    border-radius: 8px;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
    overflow: hidden;
    margin: 15px;

}

#imageSanta {
    width: 100%;
}

@media screen and (max-width: 992px) {
    .santa-card {
        width: 100%;
        height: 120px;
        background-color: #ffffff;
        border-radius: 8px;
        box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
        overflow: hidden;
        margin: 15px;

    }
}
</style>