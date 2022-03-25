<template>
  <div>
    <li>
      <div>
        <header>
          <h3>{{ title }}</h3>
          <button>Delete</button>
        </header>
      </div>
      <p>{{ description }}</p>
      <nav>
        <a :href="link">View Resource</a>
      </nav>
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
  color: #ce5c00;
}
a:hover,
a:active {
  color: #c89300;
}
</style>
