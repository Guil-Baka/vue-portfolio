<script setup lang="ts">
import horizontalNavBar from './components/horizontalNavBar.vue'
</script>

<template>
  <header>
    <!-- <img alt="Vue logo" class="logo" src="@/assets/logo.svg" width="125" height="125" /> -->

    <div class="wrapper">
      <!-- <HelloWorld msg="You did it!" /> -->
      <!-- <nav>
        <RouterLink to="/">a</RouterLink>
        <RouterLink to="/about">b</RouterLink>
      </nav> -->
      <horizontalNavBar :names="['Home', 'About']" :routerLink="['/', '/about']" />
    </div>
  </header>

  <RouterView />
</template>