<template>
    <section>
        <div class="container">
                <ul class="list-unstyled d-flex flex-wrap row justify-content-center ">
                    <li class="col-2" v-for="(element, index) in playList" :key="`list-${index}`">
                        <Card 
                        :poster="element.poster"
                        :title="element.title"
                        :author="element.author"
                        :year="element.year"
                        :genre="element.genre"
                        />
                    </li>
                </ul>
        </div>
    </section>
</template>

<script>
import axios from 'axios';
import Card from './Card.vue'

export default {
name: 'MainContent',
components: {
    Card,
},
data(){
    return {
        playList: [],
    }
},

created() {
    this.getMusic();
},

methods: {
    getMusic(){
        axios.get('https://flynn.boolean.careers/exercises/api/array/music')
        .then(response => (this.playList = response.data.response))
    }
}
}

</script>

<style scoped lang="scss">

section {
    background-color: #1d2d3c;
    padding-top: 3rem;
    flex-grow: 1;
    overflow: auto;
    li{
        margin: 1rem 0;
    }
}

</style>