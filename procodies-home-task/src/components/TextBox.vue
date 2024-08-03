<template>
  <div class="column justify-between justify-center mainFont defaultFontColor"
    :class="props.type === 'infoPanel' ? 'items-start' : 'items-center'"
    :style="{ 'width': props.styles.width || '1200px'}"
  >
    <div v-for="(headerText, index) in header"
      :key="index"
      class="textBoxHeader"
      :class="index + 1 === header.length ? 'q-mb-md' : ''"
      :style="{ 'font-size': props.styles.hFontSize }"
      v-html="highlightSpan(headerText)"
    >
    </div>
    <div v-if="props.type !== 'infoPanel'"
      class="textBoxText"
      :style="{ 'color': props.styles.color, 'text-wrap': props.styles.tWrap, 'font-size': props.styles.tFontSize  }"
    >
      {{ isTextArray ? props.text.join(`${props.separator || ' '}`)  : props.text }}
    </div>
    <div v-if="props.type === 'infoPanel'" class="column items-start" >
      <div v-for="(sectionText, index) in props.text"
        :key="index"
        :style="{'font-size': props.styles.tFontSize }"
      >
        {{ sectionText }}
      </div>
    </div>
  </div>
</template>

<script setup>
import { computed } from 'vue'

const props = defineProps(['styles', 'header', 'text', 'separator', 'type', 'span'])

const isTextArray = computed(() => Array.isArray(props.text))

function highlightSpan (text) {
  return !props.span || !text.includes(props.span.target)
    ? text
    : text.replace(
      props.span.target,
      `<span style="color: ${props.span.color}">${props.span.target}</span>`
    )
}
</script>
