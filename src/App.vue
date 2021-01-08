<template>
  <div class="main-content-area">
    <comp-landing/>
  </div>
</template>

<script>
import compLanding from './components/Landing.vue';

export default {
  name: 'App',
  components:{
    compLanding
  }
}
</script>

<style>
  @import './assets/style.css';
</style>
