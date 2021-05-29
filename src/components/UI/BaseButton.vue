<template>
  <button :mode="mode">
    <slot></slot>
  </button>
</template>

<script>

export default ({
  props: [ 'mode']
})
</script>


<style scoped>
  button {
  padding: 0.75rem 1.5rem;
  font-family: inherit;
  background-color: #ebdff3;
  color: rgb(80, 74, 74);
  cursor: pointer;
  border-radius: 10px;
  outline: none;
}

button:hover,
button:active {
  background-color: #644e74;
  border-color: #270041;
  color: #f9f5fc;
  transition: .5s;
}

.flat {
  background-color: transparent;
  color: #3c1c52;
  border: none;
}

.flat:hover,
.flat:active {
  background-color: #edd2ff;
}
</style>
