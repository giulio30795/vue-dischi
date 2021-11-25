<template>
    <section>
        <div class="container">
            <ul  v-if="playList.length  !== 0"
            class="list-unstyled d-flex flex-wrap row justify-content-center ">
                <li v-for="(element, index) in playList" :key="`list-${index}`">
                    <Card 
                    :poster="element.poster"
                    :title="element.title"
                    :author="element.author"
                    :year="element.year"
                    :genre="element.genre"
                    />
                </li>
            </ul>
            <div 
                v-else
                class="loader d-flex flex-column align-items-center justify-content-center">
                    <div>Loading...</div>
                    <svg xmlns="http://www.w3.org/2000/svg" fill="currentColor" class="bi bi-arrow-clockwise" viewBox="0 0 16 16">
                    <path fill-rule="evenodd" d="M8 3a5 5 0 1 0 4.546 2.914.5.5 0 0 1 .908-.417A6 6 0 1 1 8 2v1z"/>
                    <path d="M8 4.466V.534a.25.25 0 0 1 .41-.192l2.36 1.966c.12.1.12.284 0 .384L8.41 4.658A.25.25 0 0 1 8 4.466z"/>
                    </svg>
            </div>
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
        width: calc(100% / 8);
    }
}

.loader{
    color:white;
    font-size: 3rem;
    svg{
        width: 200px;
        height: 200px;
    }
}

</style>