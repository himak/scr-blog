<template>
  <div class="not-found">
    <h1>404</h1>
    <p>Sorry, not found :(</p>
  </div>
</template>

<style scoped lang="scss">
$bg-color: #fdefe6;
$text-color: #020500;

.not-found {
  background-color: $bg-color;
  color: $text-color;
  min-height: calc(100vh - 100px);
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
</style>
