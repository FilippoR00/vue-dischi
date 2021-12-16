<template>
    <div>
        <img src="../assets/logo.png" alt="logo">
    </div>
</template>

<script>
export default {
    name: 'Header',
}
</script>

<style scoped lang="scss">
    @import '../assets/style/global.scss';
    div{
        height: 70px;
        background-color: $mainColor;
        padding: 10px 20px;
        img{
            height: 100%;
        }
    }
</style>