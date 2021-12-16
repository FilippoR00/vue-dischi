<template>
    <div class="card">
        <img :src="cardInfo.poster" :alt="cardInfo.title">
        <div class="title">{{cardInfo.title}}</div>
        <div class="auth">{{cardInfo.author}}</div>
        <div class="year">{{cardInfo.year}}</div>
    </div>
</template>

<script>
export default {
    name: 'Card',
    props: {
        cardInfo : Object
    }
}
</script>

<style scoped lang='scss'>
    .card{
        padding: 20px 10px;
        img{
            width: 100%;
        }
        .title{
            text-transform: uppercase;
            font-size: 22px;
            font-weight: 600;
            margin: 20px 0px;
        }
        .auth{
            color: gray;
            font-size: 18px;
        }
        .year{
            color: gray;
        }
    }
</style>