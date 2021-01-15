<template>
  <div id="app">
    <h2>Известные кинокомпании</h2>
    <v-carousel
    :carousel_data="sliderItems"
    :interval="2000"
    :slideWidth="300"
    />
  </div>
</template>

<script>
import VCarousel from './components/v-carousel.vue'


export default {
  name: 'App',
  data(){
    return{
      sliderItems: [
        {id:1, rating: 8.5, name: 'Universal', img: '1.jpeg'},
        {id:2, rating: 7.3, name: 'Warner Brosers', img: '2.jpeg'},
        {id:3, rating: 8.2, name: 'Disney', img: '3.jpeg'},
        {id:4, rating: 6.5, name: 'Fox Networks', img: '4.jpeg'},
        {id:5, rating: 9.1, name: 'HBO', img: '5.jpeg'},
      ]
    }
  },
  components: {
    VCarousel

  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
