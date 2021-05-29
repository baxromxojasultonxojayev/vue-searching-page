<template>
  <header>
    <h1>{{title}}</h1>
  </header>
</template>

<script>
export default {
  props: ['title']
}
</script>

<style scoped>
  header{
    width: 100%;  
    height: 5rem;
    background: #4c52a5;
    display: flex;
    justify-content: center;
    align-items: center;
    box-shadow: 0 3px 4px rgba(0, 0, 0, 0.253,);
    
  }

  h1{
    padding: 50px;
    color: rgba(252, 252, 252, 0.747);
  }
</style>