<template>
  <section class="wrapper">
    <div class="wrapper__carousel" :style="{'margin-left': '-' + (100 * currentSlideIndex) + '%'}">
      <WrapperItem 
      v-for="item in carouselData"
      :key="item.id"
      :itemData="item"
    />
    </div>
    <button class="wrapper__button" @click="previosSlide" >prev</button>
    <button class="wrapper__button" @click="nextSlide">next</button>
  </section>
</template>

<script>
import WrapperItem from './WrapperItem.vue'


export default {
  name:'Wrapper',
  components: { 
    WrapperItem 
  },
  data(){
    return {
      currentSlideIndex: 0
    }
  },
  props:{
    carouselData:{
      type: Array,
      default: ()=>[]
    }, 
    interval:{
      type:Number,
      default:0
    }
  },
  mounted(){
    if(this.interval > 0){
      let context = this;
      setInterval(function(){
        context.nextSlide()
      }, context.interval)
    }
  },
  methods:{
    previosSlide(){
      if (this.currentSlideIndex > 0){
        this.currentSlideIndex--
      }
    },
    nextSlide(){
      if( this.currentSlideIndex === this.carouselData.length - 1 ){
        this.currentSlideIndex = 0
      } else {
        this.currentSlideIndex++
      }
    }
  }
}
</script>

<style>
.wrapper{
  max-width: 500px;
  overflow: hidden;
  margin: 0 auto;
}

.wrapper__carousel{
  display: flex;
  transition: all ease .5s;
}
</style>