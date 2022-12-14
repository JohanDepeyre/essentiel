<template>
    <div>
        <div class="recipe-card">
            <img :src="recipe.image" alt="Image de la recette" class="recipe-card-image">
            <div class="recipe-card-body">
                <h5 class="recipe-card-title">{{ recipe.title }}</h5>
                <p class="recipe-card-description">{{ recipe.description }}</p>
                <a href="#" class="recipe-card-button">Voir la recette</a>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'RecipeCard',
    props: {
        recipe: {
            type: Object,
            required: true
        }
    }
}
</script>

<style>
/* Définissez les styles pour le composant */
.recipe-card {
    width: 200px;
    background-color: #fff;
    border-radius: 8px;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
    overflow: hidden;
    margin: auto;
}

.recipe-card-image {
    width: 100%;
    height: 120px;
    object-fit: cover;
}

.recipe-card-body {
    padding: 16px;
}

.recipe-card-title {
    margin: 0;
    font-size: 16px;
    font-weight: bold;
}

.recipe-card-description {
    margin: 8px 0 0 0;
    font-size: 14px;
    color: #666;
}

.recipe-card-button {
    display: block;
    margin: 16px auto 0 auto;
    padding: 8px 16px;
    background-color: #0097e6;
    color: #fff;
    text-decoration: none;
    border-radius: 4px;
}

.recipe-card-button:hover {
    background-color: #0083c0;
}
</style>
