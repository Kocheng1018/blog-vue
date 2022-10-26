<script setup lang="ts">
import Copied from './components/Copied.vue'
</script>

<template>
  <Copied target="Kocheng" targetName="名字">
    點我複製名字 Kocheng
  </Copied>
  <Copied>
    點我複製網址
  </Copied>
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
