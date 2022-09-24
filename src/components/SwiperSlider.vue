<template>
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
</template>

<script>
import SwiperCore, {Autoplay} from 'swiper';

import {Swiper, SwiperSlide} from 'swiper/vue';

import 'swiper/css'

SwiperCore.use([Autoplay])
export default {
    components: {
        Swiper,
        SwiperSlide,
    },
    name: 'swip-car',
  
}
</script>

<style>

</style>