<template>
    <div class="search-bar">
        <form class="my-3">
            <span>Seleziona il genere: </span>
            <select name="Genre" v-model="selected" @change="$emit('genre', selected)">
                <option value="Rock">Rock</option>
                <option value="Pop">Pop</option>
                <option value="Jazz">Jazz</option>
                <option value="Metal">Metal</option>
            </select>
        </form>
    </div>
</template>

<script>
export default {
    name: 'Search',
    data() {
        return {
            selected : '',
        }
    } 
}
</script>

<style scoped lang="scss">
    @import 'src/assets/style/Global.scss';
    .search-bar{
        display: flex;
        justify-content: center;
        form{
            color: white;
            text-transform: uppercase;
            font-family: Arial, Helvetica, sans-serif;
            select{
                border: none;
                border-radius: 10px;
                color: white;
                background-color: $mainColor;
                width: 100px;
                text-align: center;
                padding: 5px;
                font-size: 18px;
                margin-left: 10px;
            }
        }
    }

</style>