<template>
    <div>
        <h1>Liste de recettes</h1>
        <div class="recipes-list">
            <recipe-card v-for="recipe in recipes" :key="recipe.id" :recipe="recipe" />
        </div>
    </div>
</template>

<script>
import RecipeCard from './RecipeCard'

export default {
    name: 'RecipesList',
    components: {
        RecipeCard
    },
    data() {
        return {
            recipes: [
                {
                    id: 1,
                    title: 'Tarte aux pommes',
                    description: 'Une délicieuse tarte aux pommes faite maison.',
                    image: 'https://example.com/apple-pie.jpg'
                },
                {
                    id: 2,
                    title: 'Lasagnes',
                    description: 'Des lasagnes à la bolognaise faites maison.',
                    image: 'https://example.com/lasagna.jpg'
                },
                // Ajoutez d'autres recettes ici...
            ]
        }
    }
}
</script>

<style>

</style>