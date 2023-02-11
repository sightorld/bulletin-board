<script setup lang="ts">
const columnAmountRaw = ref(0);
onMounted(() => {
  const resizeObserver = new ResizeObserver((divs) => {
    for (const div of divs) {
      if (div.contentBoxSize) {
        let widthWithoutGaps = div.contentRect.width - (Math.floor(div.contentRect.width / 250) - 1) * 24; 
        columnAmountRaw.value = Math.floor(widthWithoutGaps / 250);
      }
    }
  })

  let divRes = document.getElementById("page-name");
  if (divRes)
    resizeObserver.observe(divRes);
})

const columnAmount = computed(() : number => {
  if (process.client && columnAmountRaw.value) {
    return columnAmountRaw.value;
  }
  return 1;
})

</script>

<template>
  <div class="wrapper">
    <div class="page-name" id="page-name">
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
      <div class="post-columns-grid">
        <div class="post-column" v-for="col in columnAmount" :key="'top-col-' + col">
          <AtomsSinglePost/>
        </div>
      </div>
    </div>
    <div class="recent-posts">
      <div class="recent-posts-name">
        Последние посты
      </div>
      <div class="post-columns-grid">
        <div class="post-column" v-for="col in columnAmount" :key="'top-col-' + col">
          <AtomsSinglePost/>
          <AtomsSinglePost/>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped lang="scss">
.post-columns-grid {
  display: grid;
  column-gap: 24px;
  grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
  .post-column {
    display: flex;
    flex-direction: column;
    height: fit-content;
  }
}

.recent-posts {
  margin-top: 24px;
  padding: 0 64px;
  .recent-posts-name {
    text-align: left;
    font-weight: 400;
    font-size: 20px;
    line-height: 26px;
    color: $active-text-color;
  }
}
.wrapper {
  height: fit-content;
  margin: 0;
}

.page-name {
  font-weight: 500;
  font-size: 40px;
  line-height: 48px;
  margin: 36px 64px 0;
  text-align: left;
}

.top-posts {
  margin: 74px 0 24px;
  padding: 0 64px;
  padding-bottom: 24px;
  border-bottom: 2px solid $lighter-bg-color;
  .top-categories {
    display: flex;
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
}
</style>