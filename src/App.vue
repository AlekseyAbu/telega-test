<template>
  <body>
    <Header />
    <News v-bind:articles="articles"/>
    <Point />
    <Sorting v-bind:blocks="blocks"/>
  </body>
</template>

<script>
import Header from './components/Header.vue'
import News from './components/News.vue'
import data from '@/data/data.json'
import Point from '@/components/Point.vue'
import Sorting from '@/components/Sorting.vue'
import items from '@/data/items'

export default {
  name: 'App',
  components: {
    Header,
    News,
    Point, 
    Sorting
  },
  data(){
    return{
      articles: data,
      blocks: items
    }
  }
}
</script>

<style>
body{
  background: #F4F4F4;
  margin: 0;
  padding: 0;
}
</style>
