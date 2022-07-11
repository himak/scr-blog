<template>
  <ul class="hero">
    <HeroItem />
  </ul>
</template>

<script setup lang="ts">
import HeroItem from '@/components/hero/HeroItem.vue';
</script>

<style lang="scss">
.hero {
  list-style: none;
  padding-left: 0;
  display: flex;
  gap: 0.4em;
}

@media (max-width: 768px) {
  .hero {
    flex-wrap: wrap;
    gap: 0;

    .hero-item {
      width: 50%;
      padding: 1%;
    }
  }
}
</style>
