<template>
  <div class="row q-mb-md" :style="{ ...props.sizes }">
    <div v-if="isPictureOnLeft">
      <img :src="imageUrl" :width="props.image.imageWidth" :height="props.image.imageHeight"/>
    </div>
    <div v-if="isPictureOnLeft" class="column justify-center q-ml-md">
      <TextBox :header="props.header" :text="props.text" :span="props.span" :styles="{ ...props.styles }" type="infoPanel"/>
    </div>

    <div v-if="!isPictureOnLeft" class="column justify-center q-ml-md">
      <TextBox :header="props.header" :text="props.text" :span="props.span" :styles="{ ...props.styles }" type="infoPanel" />

    </div>
    <div v-if="!isPictureOnLeft">
      <img :src="imageUrl" :width="props.image.imageWidth" :height="props.image.imageHeight"/>
    </div>
  </div>
</template>

<script setup>
import { computed } from 'vue'
import TextBox from './TextBox.vue'

const props = defineProps(['picturePosition', 'styles', 'header', 'text', 'image', 'type', 'span'])

const isPictureOnLeft = computed(() => props.picturePosition === 'left')
const imageUrl = computed(() => `/images/${props.image.imageName}`)
</script>

<style>
.header {
font-family: 'Roboto';
font-size: 42px;
font-weight: 700;
text-align: left;
}

.text {
font-family: 'Roboto';
font-size: 16px;
font-weight: 400;
line-height: 24px;
text-align: left;
}
</style>
