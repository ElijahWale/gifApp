<template>
<div class="app" >
<Header />
 <search @fetch-gifs="onFetch"/>
  <Giflist :gifs=gifs />
   <!-- <div class="container"> -->
        
    <!-- </div> -->
  

</div>
  
</template>

<script>
import Header from './components/Header.vue'
import Search from './components/Search.vue'
import Giflist from './components/Giflist.vue'

export default {
  name: 'App',
  components: { Header, Search, Giflist },
  data() {
    return {
      gifs: [],
      isActive:true
    }
  },
  methods: {
    onFetch(result){
      this.gifs = result;
    },
    
  },
 
}
</script>

<style>
 
*{
  box-sizing: border-box;
  padding: 0;
  margin: 0;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}



</style>
