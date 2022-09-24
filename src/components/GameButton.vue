<template>
    <div class="btn-game">
        <img v-if="this.activeButton === this.imageGold.active" 
             :src="imageGold.src"
             @click="updateActiveButton">
        <img v-else 
             :src="image.src" 
             @click="updateActiveButton">
    </div>
</template>

<script>
export default {
    name: 'game-button',
    props: {
        image: {
            type: Object,
        },
        imageGold: {
            type: Object,
        },
        activeButton: {
            type: String
        }
    },
    methods: {
        updateActiveButton() {
            this.$emit('onUpdateButton',this.imageGold.active)
        }
    }
}
</script>

<style>
.btn-game {
    width: 100%;
}
.btn-game img {
    width: 100%;
    object-fit: contain;
}
@media screen and (max-width: 767.98px) {
 .btn-game {
    width: 6rem;
 }
}

@media screen and (max-width: 575.98px) {
    .btn-game {
        width: 4rem;
    }
}
@media screen and (max-width: 400px) {
    .btn-game {
        width: 2rem;
    }
}


</style>