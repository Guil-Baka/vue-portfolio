<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import { defineProps } from 'vue'

const props = defineProps<{
  names: string[]
  routerLink: string[]
}>()

// for each name in props.names, create a routerlink pointing to that page
const links = props.names.map((name, index) => {
  return {
    name: name,
    link: props.routerLink[index]
  }
})

</script>
<template>
  <div>
    <nav>
      <ul>
        <li v-for="link in links" :key="link.name">
          <RouterLink :to="link.link">{{ link.name }}</RouterLink>
          <underline class="underline">

          </underline>
        </li>
      </ul>
    </nav>    
  </div>
</template>

<style scoped>
nav {
  display: flex;
  justify-content: space-around;
  background-color: blueviolet;
}

nav ul {
  display: inline-flex;
  list-style: none;
  padding: 0;
  margin: 0;
  background-color: brown;
}

nav li {
  margin: 0;
  padding: 0;
  border-bottom: 5px solid black;
  /*disable hyperlink blue tint after click */
  text-decoration: none; 
}
nav a.router-link-exact-active {
  color: var(--color-text);
  text-decoration: none;
}

nav a.router-link-exact-active:hover {
  text-decoration: none;
  background-color: transparent;
}


@media (min-width: 1024px) {
  header {
    display: flex;
  }
}


</style>