<script>
import 'bootstrap/dist/css/bootstrap.min.css';
import 'bootstrap/dist/js/bootstrap.bundle.min.js';
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import { cards } from './components/store.js'
export default {
  components:{
    AppHeader,
    AppMain,
    cards,
  }  
}
</script>
<template>
  <div>
    <AppHeader />
    <AppMain />
  </div>
</template>
<style lang="scss">
@use '../styles/partials/generals.scss'
</style>