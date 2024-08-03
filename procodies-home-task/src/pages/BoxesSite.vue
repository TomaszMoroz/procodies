<template>
  <div class="row justify-center" style="width: 1200px">
    <EnterDetails :styles="styles.enterDetails"/>
    <TextBox :styles="styles.textBox" :header="headers.textBox" :text="texts.textBox" :separator="separator" class="q-my-md"/>
    <InfoPanel picturePosition="left" :header="headers.infoPanel1" :text="texts.infoPanel1" :image="infoPanelImages.panel1" :styles="styles.infoPanel" :span="spans.infoPanel" type="infoPanel"/>
    <InfoPanel picturePosition="right" :header="headers.infoPanel2" :text="texts.infoPanel2" :image="infoPanelImages.panel2" :styles="styles.infoPanel" :span="spans.infoPanel" type="infoPanel"/>
    <InfoPanelBottom :cards="infoPanelBottomCards" :styles="styles.infoPanelBottom"/>
    <BoxesFooter :image="boxesFooterImage" :text="texts.boxesFooter" :styles="styles.boxesFooter"/>
  </div>
</template>

<script setup>
import EnterDetails from 'src/components/EnterDetails'
import TextBox from 'src/components/TextBox.vue'
import InfoPanel from 'src/components/InfoPanel.vue'
import InfoPanelBottom from 'src/components/InfoPanelBottom.vue'
import BoxesFooter from 'src/components/BoxesFooter.vue'
import { content } from './content'

const { headers, spans, texts, infoPanelImages, infoPanelBottomCards, boxesFooterImage, styles, separator } = content
</script>
