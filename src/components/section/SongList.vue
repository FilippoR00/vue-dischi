<template>
    <div class="container">
        <Search @genre="searchGenre"/>
        <div class="loader" v-if="!fullyCharged">Loading..</div>
        <div class="row" v-if="fullyCharged">
            <div class="card_box" v-for="(track, index) in songFiltered" :key="index">
                <Card :cardInfo='track'/>
            </div>
        </div>
    </div>
</template>

<script>
import Card from '../commons/Card.vue'
import Search from '../commons/Search.vue'
import axios from 'axios';

export default {
    name: 'SongList',
    components: {
        Card,
        Search
    },
    data() {
        return {
            song: null,
            fullyCharged: false,
            selected: ''
        }
    },
    created() {
        axios.get('https://flynn.boolean.careers/exercises/api/array/music')
        .then((response) => {
            this.song = response.data.response;
            if (response.data.response.length == 10) {
                this.fullyCharged = true;
            }
        })
        .catch(function (error) {
            // handle error
            console.log(error);
        });
    },
    methods: {
        searchGenre(payload){
            this.selected = payload;
        }
    },
    computed: {
        songFiltered() {
            const array = this.song.filter( (elm) => {
                return elm.genre.toLowerCase().includes(this.selected.toLowerCase()); // true o false
            } );  // se è true mantengo il personaggio altrimenti lo scarto
            return array;
        }
    }
}
</script>

<style scoped lang="scss">
    @import 'src/assets/style/Global.scss';
    .container{
        position: relative;
        .loader{
            color: white;
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            font-family: Arial, Helvetica, sans-serif;
            font-size: 40px;
            padding: 50px;
            background-color: $mainColor;
            border-radius: 30px;
        }
        .row{
            padding: 30px 50px;
            display: flex;
            flex-wrap: wrap;
            gap: 40px;
            .card_box{
                color: white;
                text-align: center;
                width: calc(100% / 5 - 40px);
                font-family: Arial, Helvetica, sans-serif;
                background-color: $mainColor;
            }
        }
    }    
</style>