<template>
  <div class="wrapper">
    <main class="main-container">
     <nav-bar/>

      <div class="carousel-container">
        <swiper
           :autoplay="{
            delay:1000,
            disableOnInteraction: false,
            paueOnMouseEnter:true
           }"
          >
              <swiper-slide>
                  <img src="../assets/swiper.png" alt="this is an image">
              </swiper-slide>
              <swiper-slide>
                  <img src="../assets/swiper.png" alt="this is an image">
              </swiper-slide>

              <swiper-slide>
                  <img src="../assets/swiper.png" alt="this is an image">
              </swiper-slide>
          </swiper>
      </div>

      <div class="roulet-container">
        <div class="title">Hot Game</div>
        <div class="roulet-games">
          <roulet-game v-for="roulet in roulet_games"/>
        </div>
      </div>

      <div class="info">
        <div class="user-info">
          <img class="info-img" src="../assets/ho_mo@3x.png" alt="">
            <p>User Name</p>
        </div>

        <img src="../assets/téléchargement.png" alt="">
        <div class="user-info">
          <img class="info-img" src="../assets/ho_mo@3x.png" alt="">
          <p>Dragon Boat Festival holiday!holiday!</p>
        </div>
      </div>

      <div class="game-container">
        <div class="side-bar">
          <game-button v-for="button in buttons" 
                       :key="button" 
                       :image="images[button-1]"
                       :imageGold="imagesGold[button-1]"
                       :active-button="activeButton" 
                       @onUpdateButton="updateActiveButton"
                       />
        </div>

        <div class="games">
          <div v-if="this.activeButton === 'live' || this.activeButton === 'lottery'">
            <game1/>
          </div>
          <div v-else-if="this.activeButton === 'sport' || this.activeButton === 'poker'">
            <game2/>
          </div>
          <div v-else-if="this.activeButton === 'game' || this.activeButton === ''">
            <game/>
          </div>
        </div>
      </div>
    </main>
    <bottom-bar/>
  </div>
</template>

<script>

import RouletGame from '../components/RouletGame.vue'
import NavBar from '@/components/NavBar.vue';
import GameButton from '@/components/GameButton.vue';
import Game1 from '@/components/Game1.vue';
import Game2 from '@/components/Game2.vue';
import Game from '@/components/Game.vue';
import BottomBar from '@/components/BottomBar.vue';
import SwiperSlider from '@/components/SwiperSlider.vue';

import SwiperCore, {Autoplay} from 'swiper';

import {Swiper, SwiperSlide} from 'swiper/vue';

import 'swiper/css'

SwiperCore.use([Autoplay])


export default {
  name: 'HomeView',
  components: {
    RouletGame,
    NavBar,
    GameButton,
    Game1,
    Game2,
    Game,
    BottomBar,
    SwiperSlider,
    Swiper,
    SwiperSlide,

},
  data() {
    return {
      buttons: 5,
      roulet_games: 4,
      activeButton:'live',
      images: [{id:1,src:require("../assets/game_button/ho_li2@3x.png")},
              {id:2,src:require("../assets/game_button/ho_sp2@3x.png")},
              {id:3,src:require("../assets/game_button/ho_lo2@3x.png")},
              {id:4,src:require("../assets/game_button/ho_po2@3x.png")},
              {id:5,src:require("../assets/game_button/ho_ga2@3x.png")}],

      imagesGold: [{src:require("../assets/game_button/ho_li1@3x.png"), active:'live'},
              {src:require("../assets/game_button/ho_sp1@3x.png"),active:'sport'},
              {src:require("../assets/game_button/ho_lo1@3x.png"),active: 'lottery'},
              {src:require("../assets/game_button/ho_po1@3x.png"),active: 'poker'},
              {src:require("../assets/game_button/ho_ga1@3x.png"),active: 'game'}],
    }
  },
  methods: {
    updateActiveButton(name){
      if(this.activeButton === '') {
        this.activeButton = name
      } else if(this.activeButton === name) {
        this.activeButton = ''
      } else {
        this.activeButton = name
      }
    }
  },
}
</script>

<style scoped>
.wrapper {
  margin-left: 1.5rem;
  margin-right: 1.5rem;
  background-color: white;
}
.main-container {
  background-color: rgb(26 26 26 );
}
.navbar{
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.box {
  max-width: 100%;
  cursor: pointer;
}
.carousel-container{
  margin-right: auto;
  margin-left: auto;
}
img {
  max-width: 100%;
}
.title {
  font-size: 3rem;
  padding: 1rem;
  line-height: 1;
  color: #EBD193;
  text-align: left;
}
.roulet-container {
  background-color: rgb(48 48 50);
  margin-top: 0.5rem;
  border-radius: 1rem;
 
}
.roulet-games {
  display: flex;
  gap: 15px;
  padding-left: 0.5rem;
  padding-bottom: 0.5rem;
}
.info {
  background-color: rgb(48 48 50);
  margin-top: 0.5rem;
  border-radius: 1rem;
  display: flex;
}
.user-info {
  display: flex;
  align-items: center;
  gap: 20px;
  padding: 2rem;
  width: 50%;
  font-style: italic;
  color: #EBD193;
  font-weight: bold;
}
.info-img {
  width: 50px;
}
.game-container {
  background-color: rgb(48 48 50);
  margin-top: 0.5rem;
  border-radius: 1rem;
  display: flex;
  gap: 5rem;
}
.side-bar {
  padding-left: 1rem;
  padding-top: 1.2rem;
  display: flex;
  flex-direction: column;
  gap: 4rem;
}
.games {
  padding-top: 1.5rem;
  display: flex;
  flex-direction: column;
  gap: 1.2rem;
}
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


@media screen and (max-width: 1199.98px) {
  .side-bar {
    gap: 0.8rem;
  }
}
@media screen  and (max-width: 991.98px){
  .wrapper {
    margin-left: 0.2rem;
    margin-right: 0.2rem;
  }
  .side-bar {
    gap: 0.3rem;
  }
 
  .game-container {
    gap: 4rem;
  }
}

@media screen and (max-width: 767.98px) {
  .wrapper {
    margin-left: 0.2rem;
    margin-right: 0.2rem;
  }
  .info-img {
    width: 30px;
  }
  .user-info{
    padding: 1.5rem;
  }
  .user-info p {
  font-size: 13px;
  overflow-wrap: break-word;
  }
  .title{
    font-size: 20px;
  }
  .side-bar {
    gap: 0.3rem;
  }
  .game-container {
    gap: 1rem;
  }
  .games {
    width: 77vw;
    padding-top: 0.5rem;
    padding-bottom: 0.5rem;
    gap: 1rem;
  }
}
@media screen and (max-width: 575.98px){
  .user-info {
    padding: 1rem;
    gap: 0.5rem;
  }
  .user-info p {
    font-size: 10px;
    overflow-wrap: break-word;
  }
  .side-bar {
    gap: 0.2rem;
    padding-left: 0.5rem;
  }
 
}


</style>