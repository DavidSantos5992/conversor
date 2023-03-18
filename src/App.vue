<template>
  <div id="app">
    <Conversor moedaA="USD" moedaB="BRL"/>
  </div>
</template>

<script>

import Conversor from './components/Conversor.vue';

export default {
  
  name: "app",
  components:{
    Conversor
  }
  
}
</script>

<style scoped>

  #app{
    font-family: Arial, Helvetica, sans-serif;
  }

</style>
