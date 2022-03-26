<template>
  <div>
    <li>
      <base-card>
        <header>
          <h3>{{ title }}</h3>
          <!-- base button can also accept a prop named mode and we can change the looks of the button -->
          <base-button @click="deleteResource(id)">Delete</base-button>
        </header>
        <p>{{ description }}</p>
        <nav>
          <a :href="link">View Resource</a>
        </nav>
      </base-card>
    </li>
  </div>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      required: true,
    },
    description: {
      type: String,
      required: true,
    },
    link: {
      type: String,
      required: true,
    },
    id: {
      required: true,
    },
  },
  inject: ['deleteResource'],
};
</script>

<style scoped>
li {
  margin: auto;
  max-width: 40rem;
}
header {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
p {
  margin: 0.5rem 0;
}
a {
  text-decoration: none;
  font-weight: bold;
  color: #6bcb77;
}
a:hover,
a:active {
  color: #76dd83;
}
</style>
