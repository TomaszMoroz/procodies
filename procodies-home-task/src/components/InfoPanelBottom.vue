<template>
  <q-card flat square :style="{ 'background': props.styles.background }" class="q-px-sm q-py-md">
    <q-card-section horizontal>
      <q-card-section v-for="(card, index) in cards" :key="index" style="width: 33.33%">
        <div class="mainFont defaultFontColor infoPanelBottomTitle">{{ card.header }}</div>
        <div :style="{ 'font-size': props.styles.tFontSize }" class="mainFont defaultFontColor infoPanelBottomText">{{ card.text }}</div>
      </q-card-section>
    </q-card-section>
  </q-card>
</template>

<script setup>
const props = defineProps(['cards', 'styles'])
</script>
