<template>
<div id="giflist">
    <gif v-for="gif in gifs" :key="gif.id" :gif=gif />
</div>
  
</template>

<script>
import Gif from './Gif.vue'

export default {
    name: "Giflist",
    components: {Gif},
    props: {
        gifs:Array
    }
}
</script>

<style>
 #giflist{
     max-width:  1200px;
     width: 90%;
     margin:  0 auto;
     margin-top: 30px;
     display: flex;
     flex-wrap: wrap;
     justify-content: space-between;

 }
</style>