<template>
  <div class="card-music">
    <span>
        <img class="image-music" :src="path_image_music(path_img)" />
    </span>
    <div class="name-music">{{music}}</div>
    <div class="name-artist">{{artist}}</div>
  </div>
</template>

<script>
export default {
  name: 'CardMusic',
  props: {
    path_img: String,
    music: String,
    artist: String
  },
  methods: {
    path_image_music: function (path) {
      let images = require.context('../assets/', false, /\.png$|\.jpg$/)
      return images("./"+path)
    }
  }
}
</script>

<style>
    .card-music {
        margin-left: 30px;
        margin-right: 30px;
        height: 100%;
        background-color: #091012;
        border-radius: 10px;
        color: rgb(153, 153, 153);
        display: block;
    }
    .card-music:hover {
        background-color: #8CB614;
        cursor: pointer;
        color: #091012;
        -webkit-transition: 0.5s ease-out;
        -moz-transition: 0.5s ease-out;
        -o-transition: 0.5s ease-out;
        transition: 0.5s ease-out;
    }
    .image-music {
        margin-top: 20px;
        border-radius: 10px;
        width: 120px;
        height: 120px;
    }
    .name-music {
        font-size: 18px;
        font-weight: bolder;
    }
    .name-artist {
        font-size: 14px;
    }

</style>