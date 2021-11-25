<template>
        <div class="card-container">
            <div class="img-container">
                <img class="" :src="poster" :alt="title">
            </div>
            <div class="text-container">
                <h3 class="fs-6">{{title}}</h3>
                <h4>{{author}}</h4>
                <h4>{{year}}</h4>
                <h5>{{genre}}</h5>
            </div>
        </div>
</template>

<script>
export default {
    name: 'Card',
props: {
    poster: String,
    title: String,
    author: String,
    year: String,
    genre: String,
},
}
</script>

<style scoped lang="scss">
.card-container{
            padding: 1rem;
            height: 100%;
            background-color: #2e3a46;
            .img-container{
                height: 50%;
                }
                img{
                    object-fit: contain;
                    width: 100%;
                    height: 100%;
                    object-position: top;
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
                    
                    font-size: .7rem;
                    color:#757776;
                }
                h5{
                    font-size: .7rem;
                }
            }
}

</style>