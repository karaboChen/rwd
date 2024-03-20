<script setup>
import { onMounted } from 'vue'

onMounted(() => {

})

</script>


<template>
  <div class="container">
    <h3>活動集錦・ALBUMS・活動集錦・ALBUMS・活動集錦・ALBUMS・活動集錦・ALBUMS</h3>
    <h3>活動集錦・ALBUMS・活動集錦・ALBUMS・活動集錦・ALBUMS・活動集錦・ALBUMS</h3>
  </div>
</template>


<style lang="scss" scoped>
.container {
  background: black;
  overflow: hidden;
  height: 55px;
  line-height: 55px;
  display: flex;
  white-space: nowrap;
  text-transform: uppercase;

  h3 {
    white-space: nowrap;
    font-weight: 700;
    font-size: 32px;
    color: #FBFF22;
    white-space: nowrap;
    animation: mq 40s linear infinite;

    &:nth-child(2) {
      animation: mq2 40s linear infinite;
      animation-delay: -20s;
    }
  }
}

@keyframes mq {
  0% {
    transform: translateX(100%);
  }

  100% {
    transform: translateX(-100%);
  }
}

@keyframes mq2 {
  from {
    transform: translateX(0%)
  }

  to {
    transform: translateX(-200%)
  }
}
</style>