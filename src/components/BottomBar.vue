<template>
    <div class="bot-bar">
        <div class="item" @click="updateActivebtn(1)">
            <img v-if="this.activeBtn === 1" src="../assets/bottom_bar/ho_ho1@2x.png">
            <img v-else src="../assets/bottom_bar/ho_ho2@2x.png" >
        </div>
        <div class="item" @click="updateActivebtn(2)">
            <img v-if="this.activeBtn === 2" src="../assets/bottom_bar/ho_ac1@2x.png"  >
            <img v-else src="../assets/bottom_bar/ho_ac2@2x.png" >
        </div>
        <div class="item" @click="updateActivebtn(3)">
            <img v-if="this.activeBtn === 3" src="../assets/bottom_bar/ho_wa1@2x.png" >
            <img v-else src="../assets/bottom_bar/ho_wa2@2x.png" >
        </div>
        <div class="item" @click="updateActivebtn(4)"> 
            <img v-if="this.activeBtn === 4" src="../assets/bottom_bar/ho_co1@2x.png" >
            <img v-else src="../assets/bottom_bar/ho_co2@2x.png" >
        </div>
        <div class="item" @click="updateActivebtn(5)">
            <img v-if="this.activeBtn === 5" src="../assets/bottom_bar/ho_my1@2x.png" >
            <img v-else src="../assets/bottom_bar/ho_my2@2x.png" >
        </div>
    </div>
</template>

<script>
export default {
    name: 'bottom-bar',
    data() {
        return {
            activeBtn: 1,
        }
    },
    methods: {
        updateActivebtn(id) {
            if(this.activeBtn === null ) {
                this.activeBtn = id
            } else if( this.activeBtn === id) {
                this.activeBtn = null
            } else {
                this.activeBtn = id
            }
        }
    }
}
</script>

<style>
.bot-bar{
    display: grid;
    grid-template-columns: repeat(5,minmax(0,1fr));
    gap: 1rem;
    border: 2px solid white;
    border-radius: 0.7rem;
    background-color: rgb(48 48 50);
    width: 96%;
    padding: 0.4rem;
    position: fixed;
    bottom: 2.5vw;

}
.item {
    width: 20%;
}
.item img{
    width: 40px;
    object-fit: contain;
}

@media screen and (max-width: 575.98px){
    .item img {
        width: 25px;
    }
}
</style>