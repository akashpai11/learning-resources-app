<template>
  <the-header title="Remember" />
  <the-resources />
</template>

<script>
import TheHeader from './components/layouts/TheHeader.vue';
import TheResources from './components/learning-resources/TheResources.vue';
export default {
  components: { TheHeader, TheResources },
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Nunito+Sans:ital,wght@0,200;0,300;0,400;0,700;1,600&display=swap');

* {
  box-sizing: border-box;
}

html {
  font-family: 'Nunito Sans', Segoe UI, Tahoma, Geneva, Verdana, sans-serif;
}

body {
  margin: 0;
}
</style>
