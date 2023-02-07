<script setup lang="ts">

</script>

<template>
  <div class="side-content">
    <div class="upper-side">
      <div class="item-with-text logo-div" @click="navigateTo('/')">
        <img src="~/assets/icons/logo.svg" alt="logo" width="40" >
        <h1 class="logo-name">BBoard</h1>
      </div>
      <AtomsNavList />
    </div>
    <div class="lower-side">
      <div class="item-with-text logout">
        <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg"> 
          <g clip-path="url(#clip0_3_339)"> <rect width="24" height="24" fill="#1A1A1A"/> <path class='inner' d="M6.5 12.004H22.25" stroke="#747474" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/> 
          <path class='inner' d="M18.5 15.754L22.25 12.004L18.5 8.254" stroke="#747474" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
          <path class='inner' d="M15.75 16.5V21C15.7671 21.3796 15.6333 21.7505 15.3776 22.0316C15.122 22.3127 14.7655 22.4811 14.386 22.5H2.11301C1.73372 22.4808 1.37743 22.3123 1.12203 22.0312C0.86663 21.7501 0.732879 21.3794 0.750014 21V3C0.732613 2.62054 0.866271 2.24964 1.12173 1.96851C1.37718 1.68737 1.73362 1.51891 2.11301 1.5H14.386C14.7655 1.51891 15.122 1.68734 15.3776 1.96845C15.6333 2.24955 15.7671 2.62044 15.75 3V7.5" stroke="#747474" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/> </g>
          <defs> <clipPath id="clip0_3_339"> <rect width="24" height="24" fill="white"/> </clipPath> </defs>
        </svg>
        <p>Log out</p>
      </div>
    </div>
  </div>
</template>

<style scoped lang="scss">
.side-content {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.upper-side{
  height: fit-content;
  margin: 40px 32px 0;
  
}

.lower-side {
  height: fit-content;
  width: fit-content;
  margin: 0 auto 40px 32px;
}
.logout {
  cursor: pointer;
  height: fit-content;

  font-style: normal;
  font-weight: 500;
  font-size: 17px;
  line-height: 20px;
  p {
    transition: 0.7s;
    color: $inactive-text-color;
  }
  .inner {
    transition: 0.7s;
    color: $inactive-text-color;
  }
  &:hover {
    p {
      color: $active-text-color;
    }
    .inner {
      stroke: $active-text-color;
    }
  }
}
.logo-div {
  cursor: pointer;
  gap: 17px;
}
.logo-name {  
  height: fit-content;
  font-size: 22px;
  font-weight: 500;
  line-height: 26px;
  letter-spacing: 0em;
  text-align: left;
  color: $active-text-color;
}


</style>