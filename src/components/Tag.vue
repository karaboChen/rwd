<script setup>
const prop = defineProps({
  word: String
})
</script>


<template>
  <div class="tag">
    <p> {{ prop.word }}</p>
  </div>
</template>


<style lang="scss" scoped>
@import '../assets/rwd.scss';

.tag {
  width: 60px;
  height: 28px;
  border: 1px solid black;
  text-align: center;
  border-left: 3px solid black;
  font-size: 14px;
  font-family: "Noto Serif TC";
  font-weight: 700;

  @include pad {
    width: 75px;
    height: 30px;
  }

  @include pc {
    width: 80px;
    height: 31px;
    font-size: 16px;
  }

  p {


    @include pc {
      transform: translateY(-8px);
    }

  }
}
</style>