
<template>
    <h1>Welcome to Shuffle Cards!</h1>
    <div v-if="card" class="card-container">
        <h1 v-if="card.value">{{card.value}} of {{card.suit}}</h1>
  <img :src="card.images.png" alt="">
</div>
<div class="pick-card-container">
<button @click="cardPick()" >Pick a Card!</button>
</div>

</template>

<script>
import axios from 'axios'
export default {
    data(){
        return{
            card:{images:{png:'https://www.pngall.com/wp-content/uploads/4/Fanned-Playing-Card-Transparent.png'}}

        }
    },
    methods:{
        async cardPick(){
            this.card = {images:{png:'https://media.tenor.com/wVKBM8TMuisAAAAi/card-queen.gif'}}
        const card = await axios.get('https://deckofcardsapi.com/api/deck/new/draw/?count=1')
        this.card = card.data.cards[0]
        console.log(this.card);
        }

    },
    async created(){

        // console.log(this.card);
        
    }
}
</script>

<style lang="scss">
.pick-card-container{
    button{
        padding:10px;
        border:none;
        font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
        font-weight: 700;
        &:hover{
            background-color: lightcoral;
        }
    }
    position: absolute;
    top: 80%;
    left: 50%;
    transform: translate(-50%,-10%);
}
h1{
    text-align: center;
    font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
}
    .card-container{
        text-align: center;
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%,-50%);
        img{
            width: 300px;
            
        }
    }
</style>