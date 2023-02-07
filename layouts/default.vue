<script setup lang="ts">

</script>

<template>
  <div class="container">
    <div class="sidebar">
      <SideBar/>      
    </div>
    <div class="page">
      <slot />
    </div>
    <div class="manager">
      <AccountManager/>
    </div>
  </div>
</template>

<style scoped lang="scss">
.container {
  display: flex;
  flex-direction: row;
  .sidebar {
    min-width: 200px;
    background-color: $lighter-bg-color;
    width: 13vw;

  }
  .page {
    background-color: $darker-bg-color;
    width: 65vw;
  }
  .manager {
    background-color: $lighter-bg-color;
    width: 22vw;
  }
}
</style>