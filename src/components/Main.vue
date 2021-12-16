<template>
    <div>
        <SongList/>
    </div>
</template>

<script>
import SongList from './section/SongList.vue'

export default {
    name: 'Main',
    components: {
        SongList
    }
}
</script>

<style scoped lang='scss'>
    @import '../assets/style/global.scss';
    div{
        background-color: $secondaryColor;
        min-height: 100vh;
    }
</style>