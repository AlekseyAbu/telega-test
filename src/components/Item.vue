<template>
    <div class="item">
        <p class="item__text">{{block.number}}</p>
    </div>
</template>

<script>
export default {
  props: ["block"],
};
</script>

<style scoped>
.item{
    background: #C4C4C4;
    position: relative;
    height: 125px;
    opacity: 1;
    transition: opacity .4s;
}
.item__text{
    position: absolute;
    left: 15px;
    bottom: 15px;
    font-family: Roboto;
    font-style: normal;
    font-weight: bold;
    font-size: 14px;
    line-height: 16px;
    margin: 0;
}
</style>