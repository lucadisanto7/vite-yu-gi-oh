<script>
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import { cards } from './components/store.js'
export default {
  AppHeader,
  AppMain,
  cards,
}
</script>
<template>
  <div>
    <AppHeader />
    <AppMain />
  </div>
</template>
<style>
  
</style>