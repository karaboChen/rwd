<script setup>
const prop = defineProps({
  title: String,
  txt: String,
  img: String,
  rotate: String
})

</script>


<template>
  <div class="box" :style="{ transform: 'rotate(' + prop.rotate + 'deg)' }">
    <span>{{ prop.title }}</span>
    <img :src="prop.img" alt="">
    <p>{{ prop.txt }}</p>
  </div>
</template>

<style lang="scss" scoped>
@import '../assets/rwd.scss';

.box {
  border: 2px solid #030303;
  width: 80%;
  margin: 0 auto;
  margin-top: 48px;
  display: flex;
  flex-direction: column;
  position: relative;
  flex-wrap: wrap;



  @include pc {
    width: 23%;
    overflow: hidden;
  }

  span {
    font-family: "Noto Serif TC";
    font-weight: 700;
    font-size: 16px;
    padding: 9.1px 16.52px;
    background-color: #FFFFFF;
    transform: rotate(-5deg);
    position: absolute;
    top: -5%;
    left: 30%;
  }

  .img {
    max-width: 100%;
    height: 100%;
    object-fit: cover;
    vertical-align: middle;
  }

  p {
    font-family: "Noto Serif TC";
    font-weight: 700;
    font-size: 18px;
    margin-top: 12px;
    margin-bottom: 32px;
  }

}
</style>