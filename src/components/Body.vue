<template>
  <div class="body-container">

      <div class="carousel-container">
        <div class="carousel">
          <button class="btn-music" v-on:click="play1">
            <CardMusic path_img='capa-gusttavo_lima.jpg' music='Inventor dos Amores' artist='Gusttavo Lima'/>            
          </button>
          <button class="btn-music" v-on:click="play2">
            <CardMusic path_img='capa-malu.jpg' music='Disco Arranhado' artist='Malu Remix Dj Lucas Beat'/>
          </button>
          <button class="btn-music" v-on:click="play3">
            <CardMusic path_img='capa-marilia_mendonca.jpg' music='Uma Vida a Mais' artist='Marília Mendonça'/>
          </button>
        </div>
      </div>

      <div class="container-list">

        <div class="list">
          <div>
            Aqui você escuta muśicas de maneira ilimitada!
          </div>
        </div>

        <Player :class="{player1}" path_music="inventor_dos_amores.mp3" path_img='capa-gusttavo_lima.jpg' music='Inventor dos Amores' artist='Gusttavo Lima'/>
        <Player :class="{player2}" path_music="disco_arranhado.mp3" path_img='capa-malu.jpg' music='Disco Arranhado' artist='Malu'/>
        <Player :class="{player3}" path_music="uma_vida_mais.mp3" path_img='capa-marilia_mendonca.jpg' music='Uma Vida a Mais' artist='Marília Mendonça'/>  
      </div>
  </div>
</template>

<script>
import Player from './Player.vue'
import CardMusic from './CardMusic'

export default {
    components: {
      Player,
      CardMusic    
    },
    data: () => ({
        player1: true,
        player2: true,
        player3: true
    }),
    methods: {
      play1: function() {
        this.player1 = false
        this.player2 = true
        this.player3 = true
      },
      play2: function() {
        this.player1 = true
        this.player2 = false
        this.player3 = true
      },
      play3: function() {
        this.player1 = true
        this.player2 = true
        this.player3 = false
      }           
    }
}
</script>

<style>
    .body-container {
        position: relative;
        width: 100%;
        height: calc(100% - 80px);
        background-color: #151A1C;
        overflow-x: auto;
    }
    .carousel-container {
        width: 100%;
        height: 250px;
        display: flex;
        overflow-x: auto;
        justify-content: center;
        align-items: center;      
    }
    .carousel {
        display: grid;
        grid-template-columns: calc(100% / 3) calc(100% / 3) calc(100% / 3);
        width: 80%;
        height: 80%;
    }
    .container-list {
        width: 100%;
        height: 550px;
        display: flex;
        justify-content: center;       
        color: rgb(109, 109, 109);    
    }
    ::-webkit-scrollbar {
        width: 10px;
    }
    ::-webkit-scrollbar-thumb {
        -webkit-border-radius: 3px;
        border-radius: 10px;
        background:#8CB614; 
    }
    .btn-music {
      background: none;
      outline: none;
      border: none;
    }

    .player1, 
    .player2,
    .player3 {
      display: none;
    }

    .list {
      width: 90%;
      height: 290px;
      background-color: #091012;
      border-radius: 15px;
      font-size: 30px;
      color: #999;
      padding-top: 30px;
    }
</style>