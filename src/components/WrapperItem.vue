<template>
  <div class="wrapper__item">
    <img 
      :src=" require('../assets/' + itemData.img)"
      class="wrapper__image"
      />
  </div>
</template>

<script>
export default {
  name: 'WrapperItem',
  props: {
    itemData:{
      type: Object,
      default: () => {},
    }
  }
}
</script>

<style>
  .wrapper__image{
    width: 500px;
    height: 300px;
    object-fit: cover;
  }
</style>