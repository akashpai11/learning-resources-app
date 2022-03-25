<template>
  <div>
    <li>
      <base-card>
        <header>
          <h3>{{ title }}</h3>
          <!-- base button can also accept a prop named mode and we can change the looks of the button -->
          <base-button>Delete</base-button>
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
  },
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
  color: #ff8080;
}
a:hover,
a:active {
  color: #e05858;
}
</style>
