<script setup>
// reference: https://vue3-carousel.ismail9k.com/getting-started.html
import 'vue3-carousel/carousel.css'
import { Carousel } from 'vue3-carousel'
import { Slide } from 'vue3-carousel' 
import { Pagination } from 'vue3-carousel' 
import { Navigation } from 'vue3-carousel'


const carouselConfig = {  // config object
  itemsToShow: 2.5,
  wrapAround: true // end wraps to the beginning
}


// hardcoded for now
const slides = [ // list of images
    {id: 1, src: "/cat-cats.png"},
    {id: 2, src: "/cat-cats.png"},
    {id: 3, src: "/cat-cats.png"},
  ]

</script>

<template> <!-- replace hardcoded array with actual data -->
<div> <!-- inline -->
  <Carousel :style="{margin:'2%'}" v-bind="carouselConfig"> <!--  -->
    <Slide v-for="slide in slides" :key="slide.id">  <!-- iterate through 10 slides -->
      
      <div>
      <img :src="slide.src" /> 
      <h3>Event Title </h3>
      <p>Description </p>
      <p>Time and Date </p>
      </div>

    </Slide>

    <template #addons> <!-- #addons is exposed -->
      <Navigation /> <!-- left and right arrows -->
      <Pagination /> <!-- circles indicating index -->
    </template>
  </Carousel>
</div>
</template>


