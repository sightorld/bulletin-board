<script setup lang="ts">

</script>

<template>
  <div class="wrapper">
    <div class="page-name">
      Объявления BBoard
    </div>
    <div class="top-posts">
      <div class="top-categories">
        <div class="top-name active">
          Топ за день
        </div>
        <div class="top-name">
          Недавно поднятые
        </div>
      </div>
    </div>
    <div class="posts-random">
      <AtomsSinglePost/>
      <AtomsSinglePost/>
      <AtomsSinglePost/>
    </div>
  </div>
</template>

<style scoped lang="scss">
.posts-random {
  display: grid;
  row-gap: 24px;
  column-gap: 24px;
  grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
}

.wrapper {
  height: fit-content;
  margin: 0 64px;
}

.page-name {
  font-weight: 500;
  font-size: 40px;
  line-height: 48px;
  margin-top: 36px;
  text-align: left;
}

.top-categories {
  display: flex;
  margin-top: 74px;
  :nth-child(2) {
    margin-left: 10px;
    padding-left: 10px;
    border-left: 2px solid $inactive-text-color;
  }
}

.top-name {
  transition: 0.5s;
  font-weight: 400;
  font-size: 20px;
  line-height: 26px;
  color: $inactive-text-color;
  &:hover {
    color: $active-text-color;
  }
}


</style>