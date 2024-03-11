<script setup>
import { RouterLink } from 'vue-router';
import { ref } from 'vue'

const is_draw = ref(false)


function fn_draw() {
  is_draw.value = is_draw ? true : false
}

</script>

<template>
  <header>
    <!-- 照片 -->
    <picture class="pic_box">
      <source srcset="/lgo_s.png" media="(max-width: 1080px)">
      <img src="/Logo.png" alt="圖片">
    </picture>

    <!-- 輸入框 -->
    <div class="input_group">
      <input type="text" placeholder="探索活動" class="input_group_txt">
      <button class="icon_box">
        <el-icon>
          <Search :color="'yellow'" />
        </el-icon>
      </button>
    </div>
    <!-- 詳細業 -->
    <nav class="link_group">
      <RouterLink :to="'#'" class="link">
        <el-icon>
          <Document />
        </el-icon>
        <span>REGISTER</span>
      </RouterLink>
      <RouterLink :to="'#'" class="link"><el-icon>
          <UserFilled />
        </el-icon>
        <span>LOGIN</span>
      </RouterLink>
    </nav>
    <!-- 漢堡排 -->
    <div class="ham_box" @click="fn_draw">
      <h2 class="ham"></h2>
    </div>
    <el-drawer v-model="is_draw" title="功能表" :direction="'ttb'" style="background-color: #F3F1E5;;">
      <h2 class="phone_link">
        <RouterLink :to="'#'" class="link">
          <el-icon>
            <Document />
          </el-icon>
          <span>REGISTER</span>
        </RouterLink>
        <RouterLink :to="'#'" class="link"><el-icon>
            <UserFilled />
          </el-icon>
          <span>LOGIN</span>
        </RouterLink>
      </h2>
    </el-drawer>
  </header>


</template>


<style lang="scss" scoped>
header {
  display: flex;
  align-items: center;
  padding: 12px;
  border-bottom: 3px solid black;
}

.phone_link{
  display: flex;
  flex-direction: column;
  row-gap: 10px;
  .link {
      display: flex;
      text-decoration: none;
      justify-content: center;
      color: black;
      width: 100%;
    }

    .link:hover{
      color: green;
    }

}


.link_group {
  display: none;
}

.ham_box {
  width: 54px;
  height: 38px;
  border: 1px solid black;
  border-radius: 5px;
  position: relative;
  cursor: pointer;

  .ham {
    width: 22px;
    height: 1px;
    border: 1px solid black;
    box-shadow: 0 8px black,
      0 -8px black;
    position: absolute;
    top: 50%;
    left: 30%;
  }
}

.input_group {
  margin: auto;

  &_txt::placeholder {
    padding: 16px 24px;
    color: #878787;
  }

  &_txt {
    width: 168px;
    height: 39px;
  }

  .icon_box {
    background-color: black;
    width: 39px;
    height: 39px;
  }

}


@media screen and (min-width: 768px) {
  header {
    padding: 24px 72px;
  }

  .ham_box {
    display: none;
  }

  .link_group {
    display: flex;

    .link {
      display: flex;
      text-decoration: none;
      color: black;
      transition: border-bottom .3s ease-out;
    }

    .link:hover{
      color: green;
      border-bottom:3px solid red ;
    }

    &> :first-child {
      transform: translateX(-24px);
    }

  }

  .input_group {
    margin-left: 5%;
    margin-right: auto;

    &_txt {
      width: 284px;
      height: 51px;
    }

    .icon_box {
      background-color: black;
      width: 51px;
      height: 51px;
    }

  }


}
</style>