<script lang="ts">
import Panel from "./components/Panel.vue";

export default {
  components: {
    Panel,
  }
}

</script>

<template>
  <header>
    <div class="wrapper">
    </div>
  </header>

  <main>
    <Panel />
  </main>
</template>

<style scoped>
header {
  line-height: 1.5;
}

main {
  background-color: aqua;
}

</style>
