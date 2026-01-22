<template>
  <nav class="navbar">
    <div class="navbar-brand">
      <h1>{{ title }}</h1>
    </div>
    <ul class="navbar-links">
      <li
        v-for="link in links"
        :key="link"
        :class="{ active: activeLink === link }"
        @click="activeLink = link"
      >
        {{ link }}
      </li>
    </ul>
  </nav>
</template>

<script>
export default {
  data() {
    return {
      activeLink: 'All',
      links: ['All', 'Milks & Dairies', 'Coffees & Teas', 'Pet Foods', 'Meats', 'Vegetables', 'Fruits']
    };
  },
  props: {
    title: {
      type: String,
      default: 'E-Commerce'
    }
  }
};
</script>

<style scoped>
.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1rem 2rem;
  border-bottom: 1px solid #eee;
  font-family: Arial, sans-serif;
}

.navbar-brand h1 {
  font-size: 1.5rem;
  color: #333;
  margin: 0;
}

.navbar-links {
  display: flex;
  list-style: none;
  margin: 0;
  padding: 0;
  gap: 2rem;
}

.navbar-links li {
  cursor: pointer;
  color: #666;
  font-weight: 500;
  transition: color 0.3s;
}

.navbar-links li:hover {
  color: #000;
}

.navbar-links li.active {
  color: #28a745;
  font-weight: bold;
  border-bottom: 2px solid #28a745;
  padding-bottom: 0.5rem;
}
</style>