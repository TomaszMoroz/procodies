<template>
  <div class="column items-center justify-center q-mt-lg">
    <div :style="{ 'font-size': styles.bFontSize }" class="q-mb-xs mainFont defaultFontColor boxesFooterText">{{ text }}</div>
    <img :src="imageURL" :height="image.imageHeight"/>
  </div>
</template>

<script setup>
import { computed } from 'vue'

const props = defineProps(['image', 'text', 'styles'])

const imageURL = computed(() => `/images/${props.image.imageName}`)
</script>
