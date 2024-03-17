<script setup>
import { ref, onMounted } from 'vue'


const data_cy = ref({
  category: '',
  data: '',
  img: '',
  subtitle: '',
  txt: ''
})


const props = defineProps({
  data: {
    type: Object,
    required: true
  }
})

onMounted(() => {
  data_cy.value = props.data
})

</script>


<template>
  <div class="box">
    <p class="title">{{data_cy.data}}</p>
    <img :src="data_cy.img" alt="" class="img">
    <p class="sec_title">{{data_cy.subtitle}}</p>
    <p class="desc">
     {{data_cy.txt}}
    </p>
    <div class="under">
      <div class="under_txt">
        <img src="/sparkler.png" alt="">
        <span>{{data_cy.category}}</span>
      </div>
      <RouterLink :to="'#'" class="link">
        <span class="sell">開賣中 >></span>
      </RouterLink>
    </div>
  </div>

</template>


<style lang="scss" scoped>
@import '../assets/rwd.scss';

.box {
  margin: 0 auto;

  @include pad {
    width: 40%;
  }

  @include pc {
    width: 32%;
  }
}

.title {
  font-family: "Yeseva One";
  font-weight: 400;
  font-size: 32px;
  border-bottom: 3px solid black;
  margin-bottom: 16px;
}

.img {
  width: 100%;
  vertical-align: middle;
}

.sec_title {
  font-family: "Noto Serif TC";
  font-weight: 700;
  font-size: 18px;
  margin: 8px 0;
}

.desc {
  font-family: "Noto Serif TC";
  font-weight: 400;
  font-size: 16px;
  line-height: 24px;
  margin-bottom: 16px;
}

.under {

  display: flex;
  justify-content: space-between;
  align-items: center;
  border-top: 2px solid black;
  border-bottom: 2px solid black;

  &_txt {
    display: flex;
    align-items: center;
  }

  &_txt>span {
    font-family: "Noto Serif TC";
    font-weight: 700;
    font-size: 16px;
  }

}

.link {
  text-decoration: none;
  font-family: "Noto Serif TC";
  font-weight: 700;
  font-size: 16px;
  color: #000000;
}
</style>