<template>
  <div id="app">
    <Header
    :genreList="genreList"
    @userselection="FilterAlbum" />

    <MainContent 
    :albumlist="test" />
  </div>
</template>

<script>
import Header from './components/Header.vue'
import MainContent from './components/MainContent.vue'
import axios from 'axios';

export default {
    name: 'App',
    components: {
        Header,
        MainContent,
    },

data(){
    return {
        playList: [],
        Choice:'',
        genreList: [],
    }
},

created() {
    this.getMusic();
},

computed:{
    test(){
        if(this.playList === ''){
            return this.playList;
            }
            else if(this.Choice === "tutti") {
                return this.playList;
            }
            else {
              return this.playList.filter(item =>{
              return item.genre.includes(this.Choice)
            })
        }
    }
},
methods: {
    getMusic(){
        axios.get('https://flynn.boolean.careers/exercises/api/array/music')
        .then((response) => { 
            this.playList = response.data.response;

            this.getGenre();
        
        })
    },

    FilterAlbum(text){
        this.Choice = text;
    },

    getGenre(){
        this.playList.forEach( element => {
            if(!this.genreList.includes(element.genre)) {
                console.log();
                this.genreList.push(element.genre)
            }
        })
    }
},
}
</script>
<style lang="scss">
@import '~bootstrap/scss/bootstrap.scss';
#app{
    height: 100vh;
    display: flex;
    flex-direction: column;
}
</style>