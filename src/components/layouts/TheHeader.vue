<template>
  <header>
    <h1>{{ title }}<span>Me</span></h1>
  </header>
</template>

<script>
export default {
  props: ['title'],
};
</script>

<style scoped>
header {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100%;
  height: 5rem;
  background-color: #fd5d5d;
}

header h1 {
  margin: 0;
  color: white;
}

header h1 span {
  color: black;
  font-weight: bold;
}
</style>
