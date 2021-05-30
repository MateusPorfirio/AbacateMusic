<template>
    <div class="player">
        <div class="container-img-player">
            <img class="img-player" :src="path_image_music(path_img)" alt="">
        </div>
        <div class="container-infos-music">
            <div class="name-music">{{music}}</div>
            <div class="name-artist">{{artist}}</div>
        </div>
        <div class="container-config-music">

            <!-- <div>
                <button v-on:click="play">Play</button>
                <button id="pause">pause</button>
                <button id="stop">stop</button>
                <button id="mais">+</button>
                <button id="menos">-</button>
                <button id="mudo">mudo</button>
            </div> -->

            <audio class="play-audio" autoplay="autoplay" controls>
                <source :src="path_music_url(path_music)" type="audio/mp3" />
                seu navegador não suporta HTML5
            </audio>
        </div>
    </div>
</template>

<script>
export default {
  name: 'CardMusic',
  props: {
    path_img: String,
    music: String,
    artist: String,
    path_music: String
  },
  methods: {
    path_image_music: function (path) {
      let images = require.context('../assets/', false, /\.png$|\.jpg$/)
      return images("./"+path)
    },
    path_music_url: function (path) {
      let musics = require.context('../assets/music', false, /\.mp3$|\.mp4$/)
      return musics("./"+path)
    },    
    play(){
        document.getElementById('audio').play();
    }
  }
}
</script>

<style>
    .player {
        width: 85%;
        height: 150px;
        background-color: #091012; 
        border-radius: 15px;
        position: fixed;
        bottom: 0;   
        margin-bottom: 40px;  
        box-shadow: 4px 0px 15px 3px #000000;  
        display: grid;
        grid-template-columns: 15% 20% 65%;
    }
    .container-img-player {
        height: 100%;
        display: flex;
        justify-content: center;
        align-items: center; 
    }
    .img-player {
        width: 100px;
        height: 100px;
        border-radius: 100px;
        border: 2px solid #8CB614;
    }
    .container-infos-music {
        margin-top: 60px;
        text-align: left;
        color: #fff;      
    }
    .container-config-music {
        height: 100%;
        background-color: #8CB614;
        border-radius: 0px 15px 15px 100px;
        display: flex;
        justify-content: center;
        align-items: center;         
    }
    .play-audio {
        outline: none;
        border: none;
        width: 500px;
    }
</style>