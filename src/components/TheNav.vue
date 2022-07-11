<script setup lang="ts">
import { RouterLink } from 'vue-router';
</script>

<template>
  <nav>
    <RouterLink to="/">Home</RouterLink>
    <RouterLink to="/about">About</RouterLink>
    <RouterLink to="/blog">Blog</RouterLink>
    <RouterLink to="/contact">Contact</RouterLink>
  </nav>
</template>

<style scoped lang="scss">
$nav-link: #000;
$nav-link-hover: #ff002c;

nav {
  a {
    font-size: 0.625em; // 10/16
    font-weight: 600;
    text-transform: uppercase;
    text-decoration: none;
    color: $nav-link;
    padding: 0.9375em; // 15/16
    transition: 0.4s;

    &:hover,
    &:focus {
      transition: 0.4s;
      color: $nav-link-hover;
    }

    &.router-link-exact-active {
      color: $nav-link-hover;
    }
  }
}
</style>
