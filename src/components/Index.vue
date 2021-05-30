<template>
  <div class="main">
    <Navbar/>
    <Body/>
  </div>
</template>

<script>
import Navbar from './Navbar.vue'
import Body from './Body.vue'

export default {
    name: 'Main',
    components: {
      Navbar,
      Body
    }
}
</script>

<style>
* {
  margin: 0;
}
.main {
    margin: 0;
    width: 100vw;
    height: 100vh; 
}
</style>