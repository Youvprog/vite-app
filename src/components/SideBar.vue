<template>
    <div class="btn-game">
        <img :src="image" alt="">
    </div>
</template>

<script>
export default {
    name: 'button-game',
    props : {
        image: String
    }
}
</script>

<style scoped>
.btn-game {
  width: 100%;
}
</style>