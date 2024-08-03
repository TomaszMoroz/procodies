<template>
  <div class="row justify-between full-width">
    <div class="column justify-center q-mr-md">
      <PictureSlider/>
    </div>
    <div class="column col">
      <div>
        <div class="enterDetailsHeader mainFont defaultFontColor" :style="{ 'font-size': styles.hFontsize }">
          Chance to win a StockX <br>
          Mystery Box today!
        </div>
        <div class="enterDetailsSubheader mainFont defaultFontColor q-my-md" :style="{ 'font-size': styles.sFontSize }">
          Unleash the Excitement of Mystery Electronics
        </div>
        <EnterDetailsForm />
      </div>
    </div>
  </div>
</template>

<script setup>
import PictureSlider from 'src/components/PicturesSlider.vue'
import EnterDetailsForm from 'src/components/EnterDetailsForm.vue'

defineProps(['styles'])
</script>
