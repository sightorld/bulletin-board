<script setup lang="ts">
const a = ref(false);

</script>

<template>
  <div class="post-wrapper">
    <div class="post-name">
      Cool post.png
    </div>
    <div class="post-content" :class="a ? 'open' : ''">
      Sometimes that's just the way it has to be. Sure, there were probably other options, but he didn't let them enter his mind. It was done and that was that. It was just the way it had to be.
    </div>
    <div class="post-rollout">
      <div class="pr-button" :class="a ? 'open' : ''" @click="a = !a">
        {{a ? 'Свернуть шею автору' : 'Посмотреть полностью' }}
      </div>
    </div>
  </div>
</template>

<style scoped lang="scss">
.post-wrapper {
  background-color: $lighter-bg-color;
  border-radius: 16px;
  padding: 16px 24px;
  margin-top: 10px;
  height: fit-content;
}

.post-content {
  text-align: justify;
  font-weight: 400;
  font-size: 18px;
  line-height: 22px;
  min-height: 5rem;
  max-height: 10rem;
  overflow-y: hidden;
  position: relative;
  &:not(.open)::after {
    position: absolute;
    bottom: 0;
    width: 100%;
    height: 1rem;
    background: linear-gradient(0deg, $lighter-bg-color 0%, rgba(253,187,45,0) 100%);
    content: '';
    display: block;
  }
  &.open {
    transition: cubic-bezier(.94,.18,.1,.86) 1s;
    max-height: 100rem;
  }
}
.pr-button {
  color: $inactive-text-color;
  display: flex;
  margin-top: 10px;
  &::after {
    align-self: center;
    margin-left: 5px;
    content: '▼';
  }
  &.open {
    
    transition: 0.5s;
    &::after {
      transition: 0.5s;
      transform: rotate(180deg);
    }
  }
}

.post-name {
  font-weight: 400;
  font-size: 24px;
  line-height: 29px;
  padding-bottom: 10px;
  margin-bottom: 10px;
  border-bottom: 1px solid $cool-color;
  text-align: left;
}
</style>