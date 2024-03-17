<script setup>


const prop = defineProps({
  title: String,
  txt: String,
})
</script>


<template>
  <div class="RecentActivities">
    <div class="RecentActivities_txt">
      <h3>{{ prop.title }}</h3>
      <p>{{ prop.txt }}</p>
    </div>
  </div>
</template>


<style lang="scss" scoped>
@import '../assets/rwd.scss';

.RecentActivities {
  padding: 0 12px;
  margin-top: 32px;

  @include pad {
    margin-top: 38px;
    padding: 0 42px;
  }

  @include pc {
    margin-top: 48px;
    padding: 0 7cap;
  }

  &_txt {
    display: flex;
    justify-content: space-between;
    align-items: center;
    border: 2px solid black;
  }

  &_txt>h3 {
    font-size: 24px;
    font-family: "Yeseva One";
    padding: 16px 0px 16px 12px;

    @include pad {
      font-size: 42px;
    }

    @include pc {
      font-size: 64px;
    }
  }

  &_txt>p {
    font-size: 16px;
    padding: 12px 18px 0px 0px;
    font-weight: 700;

    @include pad {
      font-size: 23px;
    }

    @include pc {
      font-size: 32px;
    }
  }
}
</style>