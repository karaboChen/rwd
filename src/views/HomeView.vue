<script setup>
import { ref } from 'vue'


const input = ref('')



</script>

<template>
  <h1 class="main_bg">
    <div class="text_box">
      <h2 class="title">19 MAY 2023</h2>
      <h3>
        <p>隔牆有耳-沒有草東的派對</p>
        <p>你各位聽團仔們！每次想跟朋友一起聽草東專場卻每一次都搶不到票？「草東沒有派對」永遠都是「草東沒有門票」！
          帶上啤酒、野餐墊，讓我們在Live House外面一起開場「沒有草東的派對」吧！</p>
      </h3>
    </div>

  </h1>
</template>

<style lang="scss" scoped>
@import '../assets/rwd.scss';

.main_bg {
  width: 95%;
  height: 350px;
  background-image: url('/bg_phone.png');
  background-repeat: no-repeat;
  background-position: center center;
  background-size: cover;
  margin: 0 auto;
  margin-top: 16px;

  @include pad {
    width: 85%;
    background-image: url('/bg_desktop.png');
  }

  .title {
    color: aliceblue;
    font-family: "Yeseva One";
    font-size: 32px;
    word-break: break-all;
    width: 200px;
    padding: 16px 40px;


    @include pad {
      word-break: normal;
      font-size: 60px;
      width: 470px;
      padding: 48px;
    }
  }

  h3 {
    font-family: 'Noto Serif TC';
    font-size: 18px;
    color: white;
    font-weight: 700;
    letter-spacing: 3px;
    text-align: center;

    &> :first-child {
      @include pc {
        font-size: 24px;
      }
    }

    &> :last-child {
      display: none;
      @include pad {
        display: block;
        font-size: 16px;
        font-weight: 400;
        width: 85%;
        word-break: break-all;
        margin: 0 auto;
        margin-top: 16px;
      }
    }
  }

  .text_box {
    display: flex;
    flex-direction: column;
    height: 90%;
    justify-content: space-between;
  }

}
</style>