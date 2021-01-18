<template>

 <div class= "gif" :style="`background-image: url(${gif.images.original.url})`">
   <input ref="url" readonly type="text" :value="gif.images.original.url">
   <button @click="copyUrl">Copy</button>
   
 </div>
  

</template>

<script>
export default {
  name: 'Gif',
  props: {
    gif: Object
  },
  methods: {
    copyUrl(){
      this.$refs.url.select();
      document.execCommand('copy');
      this.$refs.url.value = 'Copied!!!';
       
    }
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .gif{
    width: 240px;
    height: 240px;
    background-repeat: no-repeat;
    background-size: cover;
    margin-bottom: 40px;
    background-position: center;
    display: flex;
    justify-content: space-between;
    align-items: flex-end;
    
  }
input{
   width: 150px;
  }
</style>
