<script setup lang="ts">
import { useMainStore } from '~~/store/bulletin';

const store = useMainStore();
</script>

<template>
  <div class="wrapper">
    <p class="amongi">
      {{ store.$id }}
    </p>
  </div>
</template>

<style scoped lang="scss">
.wrapper {
  height: fit-content;
}
.amongi {
  background: $amogus;
}
</style>