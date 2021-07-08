<template>
    <section class="point">
        <div class="point__infa">
            <h3 class="point__title">TEST TITLE</h3>
            <p class="point__text">It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout. The point of using Lorem Ipsum is that it has a more-or-less normal distribution of letters,</p>
        </div>
        <img class="point__img" src="#" alt="">
    </section>
</template>

<style scoped>
.point{
    max-width: 320px;
    background: #C4C4C4;
    padding: 20px 40px;
    margin: 20px auto 0;
    display: flex;
    flex-direction: row;
}
.point__img{
    width: 130px;
    height: 130px;
    background: #fff;
}
.point__img:hover{
    width: 150px;
    transition: 1s;
}
.point__infa{
    margin-right: 16px;
}
.point__title{
    font-family: Roboto;
    font-style: normal;
    font-weight: bold;
    font-size: 14px;
    line-height: 16px;
}
.point__text{
    font-family: Roboto;
    font-style: normal;
    font-weight: normal;
    font-size: 10px;
    line-height: 12px;
}
</style>