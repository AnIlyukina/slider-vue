<template>
  <section class="carousel">
    <CarouselItem/>
  </section>
</template>

<script>
import CarouselItem from './Carousel-item.vue'


export default {
  name:'Carousel',
  components: { 
    CarouselItem 
  },
  props:{
    carousel_data:{
      type: Array,
      default: ()=>[]
    }
  }
}
</script>

<style>

</style>