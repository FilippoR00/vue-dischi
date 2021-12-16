<template>
    <div class="container">
        <div class="row">
            <div class="card_box" v-for="(track, index) in song" :key="index">
                <Card :cardInfo='track'/>
            </div>
        </div>
    </div>
</template>

<script>
import Card from '../commons/Card.vue'
import axios from 'axios';

export default {
    name: 'SongList',
    components: {
        Card
    },
    data() {
        return {
            song: null
        }
    },
    created() {
        axios.get('https://flynn.boolean.careers/exercises/api/array/music')
        .then((response) => {
            this.song = response.data.response;
        })
        .catch(function (error) {
            // handle error
            console.log(error);
        });
}
}
</script>

<style scoped lang="scss">
    @import 'src/assets/style/Global.scss';
    .container .row{
        padding: 70px 50px;
        display: flex;
        flex-wrap: wrap;
        justify-content: center;
        gap: 40px;
        .card_box{
            color: white;
            text-align: center;
            width: calc(100% / 5 - 40px);
            font-family: Arial, Helvetica, sans-serif;
            background-color: $mainColor;
        }
    }
</style>