<template>
    <nav class="navbar">
        <div style="display:flex; flex-direction:column;">
          <img class="box" src="../assets/ho_me@2x.png" alt="">
          <span class="not">0</span>
        </div>
        <div ><img class="box" src="../assets/ho_lo.png" alt=""></div>
        <div><img class="box" src="../assets/ho_li.png" alt=""></div>
    </nav>
</template>

<script>
export default {
    name: 'nav-bar'
}

</script>

<style scoped>
.navbar{
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.box {
  max-width: 100%;
  cursor: pointer;
}
.not {
  box-sizing: border-box;
  background-color: red;
  width: 30%;
  border-radius: 40%;
  font-size: 1.1rem;
  position: relative;
  top:-15px;
  right: -3px;
  animation: fadeInOut 2s infinite alternate;

}

@keyframes fadeInOut {
  0% {
    opacity: 1;
  }
  100% {
    opacity: 0.2;
  }
}

</style>