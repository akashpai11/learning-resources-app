<template>
  <stored-resources :resources="storedResources"></stored-resources>
</template>

<script>
import StoredResources from './components/learning-resources/StoredResources.vue';
export default {
  data() {
    return {
      storedResources: [
        {
          id: 'official-guide',
          title: 'Official Guide',
          description: 'The Official VUE JS docs!',
          link: 'https://vuejs.org',
        },
        {
          id: 'google',
          title: 'Google',
          description: 'The most important skill to learn is - How to Google ?',
          link: 'https://google.com',
        },
      ],
    };
  },
  components: { StoredResources },
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
