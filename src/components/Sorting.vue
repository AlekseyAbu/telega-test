<template>
    <section class="sort">
        <h3 class="sort__title">SORTING</h3>
        <div class="sort__form">
            <input class="sort__input" placeholder="Enter title name" v-model="value"/>
            <button class="sort__btn" @click="blockRemove()">X</button>
        </div>
        <!-- <div class="sort__result" > -->
            <transition-group name="block" class="sort__result">
            <Item 
                v-for="block of visibleList"
                :key="block.id"
                 v-bind:block="block"
            />
            </transition-group>
        <!-- </div> -->
    </section>
</template>

<script>
import Item from '@/components/Item.vue'

export default{
    name: 'Sorting',
    components: {
        Item
    },
    props:['blocks'],
    data(){
        return{
            value: ''
        }
    },
    methods:{
        blockRemove(){
            this.value = ''
        }
    },
    computed:{
        visibleList: function(){
                if(this.value === ''){
                    return this.blocks
                } else {
                    return this.blocks.filter(item => item.number === this.value)
                }
            }
    }
}
</script>


<style scoped>
.sort{
    max-width: 320px;
    margin: 20px auto;
    display: flex;
    flex-direction: column;
    justify-content: center;
    background: #fff;
    border-radius: 15px;
    padding: 20px;
}
.sort__title{
    font-family: Roboto;
    font-style: normal;
    font-weight: bold;
    font-size: 14px;
    line-height: 16px;
    text-align: center;
}
.sort__form{
    display: flex;
    flex-direction: row;
    align-items: center;
}
.sort__input{
    max-width: 280px;
    width: 100%;
    border: 2px solid #F4F4F4;
    box-sizing: border-box;
    border-radius: 5px;
    padding: 7px;
    font-family: Roboto;
    font-style: normal;
    font-weight: normal;
    font-size: 10px;
    line-height: 12px;
    margin-right: 20px;
}
.sort__btn{
    width: 30px;
    height: 30px;
    border: 2px solid #F4F4F4;
    box-sizing: border-box;
    border-radius: 5px;
    background-color: #fff;
    padding: 0;
}
.sort__result{
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(100px,1fr));
    grid-gap: 10px;
    margin-top: 15px;
}
</style>