<template>
     <div class="wrapper">
         <div class="v-carousel" :style="{'margin-left': '-' + (100 * currentSlideIndex) + '%'}">
             <v-carousel-item
            v-for="item in carousel_data"
            :key="item.id"
            :item_data="item"
            :imageSlide="true"
            :width="slideWidth"
            >
            <p>Company: {{item.name}}</p>
            <p>Rating: {{item.rating}}</p>
            </v-carousel-item>
         </div>
         <button @click="prevSlide">Prev</button>
         <button @click="nextSlide">Next</button>
    </div>

 
</template>

<script>
import vCarouselItem from './v-carousel-item.vue'
export default {
  components: { vCarouselItem },
    name: 'v-carousel',
    props: {
        carousel_data: {
            type: Array,
            default: () => []
        },
        interval: {
            type: Number,
            default: 0
        },
        slideWidth: {
            type: Number,
            default: 300
        }
    },
    data(){
        return {
            currentSlideIndex: 0,
        }
    },
    computed:{

    },
    methods: {
        prevSlide(){
            if(this.currentSlideIndex > 0){
                this.currentSlideIndex--
            }
        },
        nextSlide(){
            if(this.currentSlideIndex >= this.carousel_data.length - 1){
                this.currentSlideIndex = 0
            }else {
                this.currentSlideIndex++
            }
        }
    },
    mounted(){
        if(this.interval > 0){
            let innerContext = this;
            setInterval(function(){
            innerContext.nextSlide();
            },innerContext.interval)
        }
    }

}
</script>

<style lang="scss" scoped>
     .wrapper{
         max-width: 300px;
            overflow: hidden;
            margin: 0 auto;
        .v-carousel{
            display: flex;
            transition: all 1s ease;
        }
    }
</style>