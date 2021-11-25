<template>
    <section>
        <div class="container">
                <ul class="list-unstyled d-flex flex-wrap row justify-content-center ">
                    <li class="col-2" v-for="(element, index) in playList" :key="`list-${index}`">
                        <div class="card-container">
                            <div class="img-container">
                                <img class="" :src="element.poster" :alt="element.title">
                            </div>
                            <div class="text-container">
                                <h3 class="fs-6">{{element.title}}</h3>
                                <h4>{{element.author}}</h4>
                                <h4>{{element.year}}</h4>
                                <h5>{{element.genre}}</h5>
                            </div>
                        </div>
                    </li>
                </ul>
        </div>
    </section>
</template>

<script>
import axios from 'axios';

export default {
name: 'MainContent',
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
     height: 100vh;
    overflow: hidden;
    li{
        margin: 1rem 0;
        .card-container{
            padding: 1rem;
            height: 100%;
            background-color: #2e3a46;
            .img-container{
                height: 50%;
                }
                img{
                    object-fit: cover;
                    width: 100%;
                    height: 100%;
                    padding: .5rem;
                }
            .text-container{
                padding-top: 1rem;
                text-transform: uppercase;
                text-align: center;
                height: 50%;
                h3,h5{
                    color:white
                }
                h4{
                    font-size: 1rem;
                    color:#757776;
                }
                h5{
                    font-size: .7rem;
                }
            }
        }
    }
}

</style>