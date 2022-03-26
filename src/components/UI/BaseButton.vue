<template>
  <button :type="type" :class="mode" :background-color="color">
    <slot></slot>
  </button>
</template>

<script>
export default {
  props: ['type', 'mode', 'color'],
};
</script>

<style scoped>
button {
  font-family: inherit;
  border-radius: 6px;
  padding: 0.5rem;
  width: 80px;
  background-color: #fc4f4f;
  border: none;
  font-weight: bold;
  color: white;
  margin: 5px;
}

/* button:hover,
button:active {
  background-color: #f56969;
  cursor: pointer;
} */

/* another class for different looks  */
.success {
  background-color: #6bcb77;
  color: white;
  border: none;
}

.success:hover,
.success:active {
  background-color: #7be489;
}

.flat {
  background-color: transparent;
  color: black;
  border: none;
}

.flat:hover,
.flat:active {
  background-color: #7be489;
}
</style>
