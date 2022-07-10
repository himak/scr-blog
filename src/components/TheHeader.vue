<script setup lang="ts">
import TheNav from '@/components/TheNav.vue';
import TheLogo from '@/components/TheLogo.vue';
</script>

<template>
  <header>
    <TheLogo />
    <TheNav />
  </header>
</template>

<style scoped lang="scss">
$header-bg: #fff;

header {
  position: relative;
  display: flex;
  align-items: center;
  height: 6.25em; // 100/16
  background-color: $header-bg;

  .logo {
    position: absolute;
    left: 1em;
  }

  nav {
    display: flex;
    justify-content: flex-end;
    align-items: center;
    width: 100%;
    max-width: 87.5em; // 1400/16
    margin: 0 auto;
    padding-right: 1em;
  }

  @media (max-width: 768px) {
    .logo {
      width: 60px;
      height: 60px;
    }
  }
}
</style>
