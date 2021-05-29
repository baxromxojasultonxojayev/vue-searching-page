<template>

  <div>
    <the-headers title="WELCOME TO EDUCATION CENTERS IN TASHKENT"></the-headers>
    <!-- <stored-resources :resources="sortedResource"></stored-resources> -->
    <the-resources></the-resources>
  </div> 
</template>

<script>
import TheHeaders from './components/layouts/TheHeaders.vue'
import TheResources  from './components/recource-item/TheResources.vue'
export default {
  components: {
    TheHeaders,
    TheResources
  }  
}
</script>

<style>
  @import url('https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap');

  * {
    box-sizing: border-box;
  }

  html {
    font-family: 'Roboto', sans-serif;
  }

  body {
    margin: 0;
  }
</style>