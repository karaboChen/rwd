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
    <p class="title">{{ prop.title }}</p>
    <div>
      <img :src="prop.img" alt="">
    </div>
    <p>{{ prop.txt }}</p>
  </div>
</template>

<style lang="scss" scoped>
@import '../assets/rwd.scss';

.box {
  border: 2px solid #030303;
  padding: 12px 12px 0px 12px;
  position: relative;
  width: 85%;
  margin: 0 auto;

  @include pad {
    width: 45%;
    margin: 0 auto;
  }

  @include pc {
    width: 21%;
    margin: 0 auto;
  }

  .title {
    position: absolute;
    top: -4%;
    left: 36%;
    background-color: #FFFFFF;
    padding: 9.1px 16.52px;
    transform: rotate(-5deg);
    font-size: 16px;
    font-weight: 700;
    font-family: "Noto Serif TC";

    @include pc {
      top: -10%;
    }

  }

  p {
    font-size: 18px;
    font-weight: 700;
    font-family: "Noto Serif TC";
    margin-top: 12px;
    margin-bottom: 32px;
  }

  div {
    img {
      width: 100%;
      height: 100%;
      vertical-align: middle;
      object-fit: cover;
    }

  }


}
</style>