<template>
  <q-card flat class="q-pa-sm cardBorder">
    <q-card-section class="q-pa-sm">
      <div class="enterDetailsTitle mainFont defaultFontColor">
        Enter details
      </div>
    </q-card-section>
    <q-card-section class="column justify-around">
      <div class="row justify-between q-mb-md">
        <q-input dense outlined label="First name" color="black" style="width: 49%; border-radius: 10px;"></q-input>
        <q-input dense outlined label="Last name" color="black" style="width: 49%; border-radius: 10px;"></q-input>
      </div>

      <q-input dense outlined label="Street" color="black" class="q-mb-md"></q-input>

      <div class="row justify-between q-mb-md">
        <q-input dense outlined label="Postal code" color="black" style="width: 49%"></q-input>
        <q-input dense outlined label="City" color="black" style="width: 49%"></q-input>
      </div>

      <q-input dense outlined label="Phone number" color="black" class="q-mb-md"></q-input>
      <q-input dense outlined label="Email" color="black" class="q-mb-md"></q-input>
      <q-btn :style="{ 'background-color': '#006340' }"  label="Proceed to payment" class="text-white col-12 q-mb-sm"/>
    </q-card-section>
    <q-card-section class="row flex flex-center q-pt-none">
      <div class="row justify-between" style="width: 314px">
        <img v-for="logo in logos" :key="logo" :src="`/images/${logo}`" width="93.33" height="40"/>
      </div>
    </q-card-section>
  </q-card>
</template>

<script setup>
const logos = ['logo_mcafee.png', 'logo_ssl.png', 'logo_trust.png']
</script>

<style>
  .cardBorder{
    border: solid 1px #DBDBDB;
    border-radius: 10px;
  }
</style>
