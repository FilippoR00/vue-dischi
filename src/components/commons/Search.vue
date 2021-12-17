<template>
    <div class="search-bar">
        <form class="my-3">
            <span>Seleziona il genere: </span>
            <select name="Genre" v-model="genreSelected" @change="$emit('genre', genreSelected)">
                <option value="Rock">Rock</option>
                <option value="Pop">Pop</option>
                <option value="Jazz">Jazz</option>
                <option value="Metal">Metal</option>
            </select>
        </form>
        <form class="my-3">
            <span>Seleziona l'artista: </span>
            <select name="Auth" v-model="authSelected" @change="$emit('auth', authSelected)">
                <option value="Bon Jovi">Bon Jovi</option>
                <option value="Queen">Queen</option>
                <option value="Sting">Sting</option>
                <option value="Steve Gadd Band">Steve Gadd Band</option>
                <option value="Iron Maiden">Iron Maiden</option>
                <option value="Eric Clapton">Eric Clapton</option>
                <option value="Deep Purple">Deep Purple</option>
                <option value="Metallica">Metallica</option>
                <option value="Dave Weckl">Dave Weckl</option>
                <option value="Michael Jacjson">Michael Jacjson</option>
            </select>
        </form>
    </div>
</template>

<script>
export default {
    name: 'Search',
    data() {
        return {
            genreSelected : '',
            authSelected : ''
        }
    } 
}
</script>

<style scoped lang="scss">
    @import 'src/assets/style/Global.scss';
    .search-bar{
        display: flex;
        flex-direction: column;
        align-items: center;
        form{
            color: white;
            text-transform: uppercase;
            font-family: Arial, Helvetica, sans-serif;
            select{
                border: none;
                border-radius: 10px;
                color: white;
                background-color: $mainColor;
                width: 200px;
                text-align: center;
                padding: 5px;
                font-size: 18px;
                margin-left: 10px;
            }
        }
    }

</style>