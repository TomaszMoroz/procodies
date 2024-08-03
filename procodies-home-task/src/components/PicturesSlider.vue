<template>
  <div class="column justify-between q-pr-xs">
    <div class="container">
      <img src="/images/price_sticker.png" width="160" height="160" class="priceSticker" />
      <img :src="imageUrl" width="481" height="480"/>
    </div>
    <div class="row justify-between">
      <div v-for="thumbnail in thumbnails" class="thumbnail"
      :key="thumbnail.path"
      :style="{'background-image': `url(${thumbnail.path})`, 'background-size': 'cover' }"
      @click="setImageName(thumbnail.name)">
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, computed } from 'vue'

const thumbnails = [
  { path: '/images/product_box_open.png', name: 'product_box_open.png' },
  { path: '/images/product_box_small.png', name: 'product_box_small.png' },
  { path: '/images/product_box_blue.png', name: 'product_box_blue.png' }
]

const imageName = ref('product_box.png')
const imageUrl = computed(() => `/images/${imageName.value}`)

function setImageName (name) {
  imageName.value = name
}
</script>

<style>
.thumbnail{
width: 132px;
height: 132px;
border-radius: 13.94px;
border: solid 0.93px
}

.container{
  display: inline-block;
  position: relative;
}

.priceSticker{
  position: absolute;
  right: -18px;
  top: -2px;
}
</style>
