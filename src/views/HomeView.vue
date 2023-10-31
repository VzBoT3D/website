<script setup>

import 'vue3-carousel/dist/carousel.css'
import { filename } from 'pathe/utils'
import { Carousel, Slide, Navigation } from 'vue3-carousel'


const glob = import.meta.glob('@/assets/vz/*.jpg', { eager: true })
const images = Object.fromEntries(
    Object.entries(glob).map(([key, value]) => [filename(key), value.default])
)
</script>

<template>
  <div class="hero min-h-screen bg-base-200">
    <div class="hero-content flex-col lg:flex-row gap-8">
      <div>
        <div class="flex flex-col">
          <h1 class="text-5xl font-bold text-center">Welcome to VzBoT</h1>
          <button class="btn btn-primary">Get Started</button>
        </div>
        <Carousel :autoplay="10000" :wrap-around="true">
          <Slide v-for="image in images" :key="image">
            <img :src="image"/>
          </Slide>
          <template #addons>
            <navigation></navigation>
          </template>
        </Carousel>

      </div>
      <div>
        <h1 class="text-5xl font-bold">Box Office News!</h1>
        <p class="py-6">Provident cupiditate voluptatem et in. Quaerat fugiat ut assumenda excepturi exercitationem quasi. In deleniti eaque aut repudiandae et a id nisi.</p>
        <button class="btn btn-primary">Get Started</button>
      </div>
    </div>
  </div>
</template>

<style scoped>

</style>