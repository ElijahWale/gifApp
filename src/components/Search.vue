<template>
  <input type="text" placeholder="Type something to search for awesome gifs" v-model="keyword" @input="onInput">
</template>

<script>
export default {
    data() {
        return {
            keyword: '',
            timeout: null
        }
    },
    methods: {
        // debouncing
        onInput(){
            clearTimeout(this.timeout);
            this.timeout = setTimeout(() => {
                this.search();
            }, 500)
        },
        search(){
            fetch(`https://api.giphy.com/v1/gifs/search?api_key=OXV3SNciUv9EqJBEADR0d4KaaIKUpleE&q=${this.keyword}&limit=9`).then(response => response.json()).then(result => {
                console.log(result)
                this.$emit('fetch-gifs', result.data)
            });
        }
    },
//OXV3SNciUv9EqJBEADR0d4KaaIKUpleEinput
}
</script>

<style>
    input{
        margin-top: 40px;
        margin-left: 20px;
        padding: 10px 16px;
        font-size: 18px;
        outline: 0;
        border: none;
        border-bottom: 2px solid #5f5f5f;
        width: 50%;
    }
    input:focus{
        border-color: #0078;
    }
</style>