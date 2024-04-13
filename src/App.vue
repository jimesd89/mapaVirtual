<script setup lang="ts">
import MapaGlobe from "./components/MapaGlobe.vue";

</script>

<template>
<MapaGlobe/>
</template>

<style scoped>
html, body{
  margin: 0;
  padding:0;
}
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
