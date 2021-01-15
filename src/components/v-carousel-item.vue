<template>
  <div class="v-carousel-item" :style="{'min-width': width + 'px'}">
      <img 
      class="v-carousel-item__img" 
      :src="require('../assets/images/' + item_data.img)" 
      alt="Slide Image"
      v-if="imageSlide"
      >
        <div class="v-carousel-item__content" v-else>
            <slot></slot>
        </div>
  </div>
</template>

<script>
export default {
    name: 'v-carousel-item',
    props: {
        item_data: {
            type: Object,
            default: () => {}
        },
        imageSlide: {
            type: Boolean,
            default: true
        },
        width: {
            type: Number,
            default: 300
        }
    },
    data(){
        return {

        }
    },
    computed:{

    }

}
</script>

<style lang="scss" scoped>
    .v-carousel-item{
        &__img{
            width: 300px;
            height: 200px;
        }
    }
</style>