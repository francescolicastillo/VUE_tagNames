<script lang="ts">
import Panel from "./components/Panel.vue";

export default {
  components: {
    Panel,
  }
}
</script>

<template>
  <main>
    <Panel />
  </main>
</template>

<style>
html {
  height: 100vh;
}

main {
  max-width: 900px;
  margin: 40px auto;
  padding: 60px 40px;
  background-color: rgb(17, 17, 17);
  border-radius: 10px;
}

body {
  background-image: linear-gradient(to bottom left, rgb(69, 212, 255), yellow);
  margin: 0 !important;
  padding: 0 !important;
}


</style>
