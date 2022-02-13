<template>
  <section class="wrapper">
    <div class="carousel">
      <CarouselItem 
      v-for="item in carouselData"
      :key="item.id"
      :itemData="item"
    />
    </div>
  </section>
</template>

<script>
import CarouselItem from './CarouselItem.vue'


export default {
  name:'Carousel',
  components: { 
    CarouselItem 
  },
  props:{
    carouselData:{
      type: Array,
      default: ()=>[]
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

.carousel{
  display: flex;

}
</style>