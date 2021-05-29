<template>

  <ul>
    <recource-item 
      v-for="item in resources" 
      :key="item.id"
      :id="item.id"
      :title="item.title"
      :description="item.description"
      :link="item.link"></recource-item>
      
  </ul>
</template>

<script>
import RecourceItem from './RecourceItem.vue'

export default {
  inject: ['resources'],
  components:{
    RecourceItem
  }
}
</script>

<style scoped>
 ul{
   list-style: none;
   padding: 0;
   margin: 0 auto;
   max-width: 40rem;
 }
</style>