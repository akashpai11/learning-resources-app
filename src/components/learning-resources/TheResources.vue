<template>
  <base-card>
    <!-- If we add event listeners to custom components they fall through default behaviour of the root level element -->
    <base-button
      @click="setSelectedTab('stored-resources')"
      :mode="storedResButtonMode"
      >Stored Resources</base-button
    >
    <base-button
      @click="setSelectedTab('add-resource')"
      :mode="addResButtonMode"
      >Add Resource</base-button
    >
  </base-card>
  <!-- Dynamic components -->
  <!-- Keep alive is used to cache the entered data. Here we use to cache the form data if we swtich between tabs -->
  <keep-alive>
    <component :is="selectedTab"></component>
  </keep-alive>
</template>

<script>
import StoredResources from './StoredResources.vue';
import AddResource from './AddResource.vue';
export default {
  data() {
    return {
      selectedTab: 'stored-resources',
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
  methods: {
    setSelectedTab(tab) {
      this.selectedTab = tab;
    },
    // we are using provide to send this method to add resource component
    addResource(title, description, link) {
      const newResource = {
        id: new Date().toISOString(),
        title,
        description,
        link,
      };
      //   adding the resource to the beginning of an array
      this.storedResources.unshift(newResource);
      this.selectedTab = 'stored-resources';
    },
    deleteResource(id) {
      // The below approach wont work at it creates a whole new array but the provide and inject points to different array in memory and hence they only work with the old array
      // this.storedResources = this.storedResources.filter(
      //   (item) => item.id !== id
      // );

      this.storedResources.splice(id, 1);
      console.log(this.storedResources.length);
    },
  },
  components: {
    StoredResources,
    AddResource,
  },
  provide() {
    return {
      resources: this.storedResources,
      addResource: this.addResource,
      deleteResource: this.deleteResource,
    };
  },
  computed: {
    storedResButtonMode() {
      return this.selectedTab === 'stored-resources' ? 'success' : 'flat';
    },
    addResButtonMode() {
      return this.selectedTab === 'add-resource' ? 'success' : 'flat';
    },
  },
};
</script>

<style lang="scss" scoped></style>
