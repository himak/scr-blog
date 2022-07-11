<template>
  <ul class="blog-list">
    <BlogItem />
  </ul>
</template>

<script setup lang="ts">
import BlogItem from '@/components/BlogItem.vue';
</script>

<style lang="scss">
.blog-list {
  padding-top: 3em;
  list-style: none;
  padding-left: 0;
  display: flex;
  align-items: flex-start;
  flex-wrap: wrap;
  max-width: 1140px;
  margin: 0 auto;
}
</style>
