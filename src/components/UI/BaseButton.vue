<template>
  <button :type="type" :class="mode">
    <slot></slot>
  </button>
</template>

<script>
export default {
  props: ['type', 'mode'],
};
</script>

<style scoped>
button {
  font-family: inherit;
  border-radius: 6px;
  padding: 0.5rem;
  width: 80px;
  background-color: #ff8080;
  border: none;
  font-weight: bold;
  color: white;
  margin: 5px;
}

button:hover,
button:active {
  background-color: #f79494;
  cursor: pointer;
}

/* another class for different looks  */
.flat {
  background-color: transparent;
  color: #3a0061;
  border: none;
}

.flat:hover,
.flat:active {
  background-color: #edd2ff;
}
</style>
