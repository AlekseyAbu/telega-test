<template>
    <section class="news">
        <h2 class="news__title">HEADING</h2>
        <Articles 
            v-for="article of visibleList"
            :key="article.id"
            v-bind:article="article"   
        />
        <button class="news__button" @click="toggleElement()">{{isElVisible ? 'SHOW MORE' : 'HIDE'}}</button>
    </section>
</template>

<script>
import Articles from '@/components/Articles.vue'

export default {
  name: 'News',
  props:['articles'],
  components: {
    Articles
  },
  data() {
      return{
          isElVisible: false,
          start: 0,
          end: 1
      }
  },
  methods: {
      toggleElement(){
          this.isElVisible = !this.isElVisible
          console.log(this.isElVisible)
          if(!this.isElVisible){
              this.end = this.end - 1
          } else{
              this.end = this.end + 1
          }
      }
  },
  computed:{
            visibleList: function(){
                return this.articles.slice(this.start,this.end);
            }
  }
}
</script>

<style scoped>
.news{
    max-width: 360px;
    margin: 20px auto 0;
    background: #FFFFFF;
    display: flex;
    flex-direction: column;
    justify-content: center;
    border-radius: 15px;
}
.news__title{
    text-align: center;
    font-family: Roboto;
    font-style: normal;
    font-weight: bold;
    font-size: 14px;
    line-height: 16px;
    margin: 0 0 20px;
    padding-top: 20px;
}
.news__button{
    margin: 0 auto 20px;
    border: 2px solid #F4F4F4;
    border-radius: 15px;
    font-family: Roboto;
    font-style: normal;
    font-weight: normal;
    font-size: 10px;
    line-height: 12px;
    padding: 16px 46px;
    background: #FFFFFF;
}
</style>


