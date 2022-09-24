<template>
    <div class="gm">
        <img src="../assets/game-image.png" alt="">
    </div>
    <div class="gm">
        <img src="../assets/game-image.png" alt="">
    </div>
</template>


<script>
export default {
    name: 'game',
}
</script>

<style>
.gm{
  width: 70vw;
  height: 20vw;
  border-radius: 0.5rem;
  overflow: hidden;
}
.gm img {
  width: 100%;
  object-fit: contain;
}
@media screen and (max-width: 767.98px) {
  .gm {
    padding-right: 0.5rem;
    width:100% ;
  }
}
@media screen and (max-width: 575.98px){
  .gm {
    padding-right: 0.5rem;
    width: 100%;
  }
}


</style>