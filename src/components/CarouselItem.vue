<template>
  <div class="carousel__item">
    <img 
      :src=" require('../assets/' + itemData.img)"
      class="carousel__image"
      />
  </div>
</template>

<script>
export default {
  name: 'CarouselItem',
  props: {
    itemData:{
      type: Object,
      default: () => {},
    }
  }
}
</script>

<style>
  .carousel__image{
    width: 500px;
    height: 300px;
    object-fit: cover;
  }
</style>