<script setup>
import { ref } from 'vue'
import board from '../components/RecentActivities.vue'
import Card from '../components/Card.vue'
import Tag from '../components/Tag.vue'
import Mq from '../components/Marquee.vue'
import Ad from '../components/Advertise.vue'
const pic_txt = ref(
  [
    {
      pic_phnoe: '/music _phone.png',
      pic: '/music.png',
      txt: '演出'
    },
    {
      pic_phnoe: '/heart_phone.png',
      pic: '/heart.png',
      txt: '聯誼'
    },
    {
      pic_phnoe: '/museum_phone.png',
      pic: '/museum.png',
      txt: '展覽'
    },
    {
      pic_phnoe: '/cutlery_phone.png',
      pic: '/cutlery.png',
      txt: '美食'
    },

    {
      pic_phnoe: '/Vector_phone.png',
      pic: '/Vector.png',
      txt: '戶外'
    },
    {
      pic_phnoe: '',
      pic_phnoe: '',
      txt: '探索更多'
    },
  ]
)


const card_group = ref([
  {
    data: '19 MAY 2023',
    img: '/a1.png',
    subtitle: '邪典電影派對——房間',
    txt: '你有聽說過「大災難家」裡面的主角 Tommy Wiseau 製作的「史上最爛的電影」——房間嗎？在美國甚至演變成一種邪教、一種派對的形式，...',
    category: '社群活動'
  },
  {
    data: '23 MAY 2023',
    img: '/a2.png',
    subtitle: '怪舞俱樂部',
    txt: '覺得自己的舞蹈細胞異於常人？每次隨著音樂起舞身邊的人總是露出無法理解的表情？來這裡就對了！來參加這場一起跳舞的聚會，也會在每一...',
    category: '演出'
  },
  {
    data: '30 MAY 2023',
    img: '/a3.png',
    subtitle: '哈利波特馬拉松',
    txt: '每次身邊有人開啟哈利波特的話題，自己永遠都是聽不懂的那個麻瓜？看大家在討論魁地奇、用咒語鬥法的時候，自己永遠是陪笑的那個人？穿...',
    category: '聯誼'
  },
  {
    data: '12 June 2023',
    img: '/a4.png',
    subtitle: '皮卡丘排球大賽',
    txt: '還記得小時候玩的小遊戲嗎？總是有朋友吹噓自己獨孤求敗、只求一敗？是時候該展現真正的實力了！本活動採用瑞士制賽程，以絕對公平的方...',
    category: '遊戲競賽'
  },
  {
    data: '25 June 2023',
    img: '/a5.png',
    subtitle: '酒精路跑',
    txt: '身邊總是有對自己酒量有高度自信的朋友嗎？拉著他/她一起來參加酒精路跑吧！一起拍下第一杯直到倒下為止的照片，一起喝遍市區內各家極...',
    category: '社群活動'
  },
  {
    data: '9 July 2023',
    img: '/a6.png',
    subtitle: '展覽——我的房間',
    txt: '每個人的房間總會有那麼一兩個能代表自己的物事，或許是再平凡不過的牙刷、馬克杯，或許有那些別人的房間從沒出現過的小東西——那些能...',
    category: '展覽'
  }
])

const ad_group = ref([
  {
    title: '社群活動',
    txt: '無聲派對-閉閉嘴dancing',
    img: '/p1.png',
    rotate: '0'
  },
  {
    title: '藝文活動',
    txt: '拯救老店大作戰',
    img: '/p2.png',
    rotate: '2'
  },
  {
    title: '自我覺察',
    txt: '內觀修行-部落篇',
    img: '/p3.png',
    rotate: '-2'
  },
  {
    title: '聯誼活動',
    txt: '賞櫻野餐',
    img: '/p4.png',
    rotate: '2'
  },
])

const icon_group = ref([
  {
    img: '/q3.png',
    txt: '7tao.event@gmail.com'
  },
  {
    img: '/q1.png',
    txt: '09123123123'
  },
  {
    img: '/q2.png',
    txt: '7TAO七逃'
  }
])

</script>

<template>
  <!-- 大看板 -->
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
  <!-- 活動專區 -->
  <div class="Activity">
    <div class="Activity_box" :class="{ yw: index === 5 }" v-for="(image, index) in pic_txt" :key="index + '9'">
      <picture>
        <source :srcset="image.pic" media="(min-width: 576px)">
        <img :src="image.pic_phnoe" alt="" class="Activity_box_pic">
      </picture>
      <p class="Activity_box_txt" :class="{ yw_txt: index === 5 }">{{ image.txt }}</p>
    </div>
  </div>
  <!-- 近期活動 -->
  <board :title="'RECENT'" :txt="'近期活動'" />
  <!-- 活動連結 -->
  <section class="card_group">
    <Card v-for="(image, index) in card_group" :key="index + '9'" :data="image" />
  </section>
  <board :title="'ONLINE'" :txt="'線上活動'" />
  <!-- gpt -->
  <section class="gpt">
    <!-- 照片 -->
    <div class="gpt_pic">
      <source srcset="/img.png" media="(min-width: 996px)">
      <img src="/computer.png" alt="">
    </div>
    <!-- 文字區塊 -->
    <div class="gpt_context">
      <h4>切特居批踢</h4>
      <div class="tag_group">
        <Tag :word="'競賽'" />
        <Tag :word="'科技'" />
        <Tag :word="'有趣'" />
      </div>
      <p>
        最近網路上很流行的AI程式ChatGPT，可以用來聊天或是查詢、整理各種資料，不同的應用方式如雨後春筍般冒出來。
      </p>
      <p class="gpt_context_sec">
        這個活動讓大家把自己最有特色的使用方法提出來讓大家參考，也會投票出最有趣的用法。該讓其他人知道自己使用ChatGPT的姿勢才是最特別的那個了！
      </p>
      <button class="gpt_context_btn">查看活動詳情 >></button>
    </div>
  </section>
  <!-- 跑馬燈 -->
  <section class="mq">
    <Mq />
  </section>
  <!-- 卡片活動 -->
  <section class="advertise">
    <Ad v-for="(data, index) in ad_group" :key="index + '9'" :title="data.title" :img="data.img" :txt="data.txt"
      :rotate="data.rotate" />
  </section>
  <!-- 跑馬燈 -->
  <section class="mq">
    <Mq />
  </section>
  <!-- 訂閱我們 -->
  <section class="subscribe">
    <div class="subscribe_left">
      <div class="subscribe_left_text">
        <p>#FOLLOW US</p>
      </div>
      <div class="subscribe_left_content">
        <p>想第一時間獲得新奇有趣的活動資訊？
          追蹤我們的社群吧！
          也歡迎你聯繫我們，提供好玩有趣的活動企劃。
        </p>
        <ul class="symbol_box">
          <li v-for=" (data, index) in icon_group" :key="index + '9'">
            <div class="symbol">
              <img :src="data.img" alt="">
            </div>
            {{ data.txt }}
          </li>
        </ul>
      </div>
    </div>

  </section>

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

  @include pc {
    width: 90%;
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

.Activity {
  width: 95%;
  min-height: 232px;
  margin: 0 auto;
  margin-top: 32px;
  display: flex;
  flex-wrap: wrap;
  column-gap: 8px;

  @include pad {
    width: 85%;
    row-gap: 8px;
  }

  @include pc {
    flex-wrap: nowrap;
    width: 90%;
    justify-content: space-between;
  }

  .yw {
    background-color: black;
    line-height: 30px;

    @include pad {
      line-height: 40px;
    }

    @include pc {
      line-height: 65px;
    }
  }

  &_box:hover {
    cursor: pointer;
    box-shadow: 1px 1px 9px red;
  }

  &_box {
    width: 31%;
    height: 110px;
    border: 2px solid black;
    text-align: center;
    padding-top: 20px;

    @include pad {
      height: 148px;
    }

    @include pc {
      max-width: 196px;
      height: 196px;
      padding-top: 40px;
    }



    &_txt {
      font-weight: 700;
      font-size: 16px;
      padding-top: 8px;

      @include pc {
        font-size: 24px;
      }
    }

    .yw_txt {
      color: yellow;
      font-size: 24px;
      word-break: break-all;
      width: 50%;
      margin: 0 auto;
      transform: translateY(-34px);

      @include pad {
        width: 50%;
        font-size: 36px;
      }

      @include pc {
        width: 73%;
        font-size: 48px;
        transform: translateY(-75px);
      }

    }

  }

}

.card_group {
  margin-top: 24px;
  padding: 0 12px;
  display: flex;
  flex-wrap: wrap;
  row-gap: 24px;

  @include pc {
    row-gap: 48px;
    padding: 0 62px;
  }
}

.gpt {
  margin-top: 24px;
  display: flex;
  flex-direction: column;

  @include pc {
    flex-direction: row;

    max-width: 90%;
    margin: 0 auto;
    margin-top: 32px;
    align-items: end;
  }



  &_pic {
    width: 93.3%;
    margin: 0 auto;

    @include pad {
      width: 90%;
    }

    @include pc {
      width: 50%;
    }
  }

  &_pic img {
    object-fit: cover;
    width: 100%;
    height: 100%;
    vertical-align: middle;
  }

  &_context {
    font-family: "Noto Serif TC";
    font-weight: 700;
    font-size: 18px;
    line-height: 25.87px;
    padding: 0 12px;
    margin-top: 12px;

    @include pad {
      font-size: 26px;
      line-height: 32.98px;
      width: 93%;
      margin: 0 auto;
      margin-top: 12px;
    }

    @include pc {
      font-size: 32px;
      line-height: 45.98px;
      margin: 0 auto;
      margin-top: 12px;
      width: 50%;
    }

    p {
      font-family: "Noto Sans TC";
      font-size: 16px;
      font-weight: 400;
      line-height: 24px;
    }

    .gpt_context_sec {
      width: 100%;

      @include pc {
        width: 95%;
      }
    }

    &_btn {
      width: 100%;
      background-color: black;
      color: white;
      padding: 16px 0px;
      font-family: "Noto Sans TC";
      font-weight: 700;
      font-size: 16px;
      margin-top: 12px;

      @include pc {
        margin-top: 32px;

      }
    }

  }


}

.tag_group {
  display: flex;
  column-gap: 8px;
  margin-top: 8px;
  margin-bottom: 12px;
}

.mq {
  background-color: black;
  margin-top: 32px;

  @include pad {
    margin-top: 45px;
  }

  @include pc {
    margin-top: 60px;
  }
}

.advertise {
  margin-top: 48px;
  display: flex;
  flex-direction: column;
  row-gap: 20.3px;

  @include pad {
    flex-direction: row;
    flex-wrap: wrap;
    row-gap: 30px;
  }

  @include pc {
    flex-wrap: nowrap;
    row-gap: 0px;
    margin: 48px
  }
}

.subscribe {
  margin-top: 32px;
  padding: 0 12px;

  &_left {
    border: 2px solid #030303;

    &_text {
      border-bottom: 2px solid #030303;
      padding: 12px 0px 16px 12px;

      p {
        font-family: "Noto Serif TC";
        font-weight: 700;
        font-size: 24px;
      }
    }

    &_content {
      padding: 16px 0px 0px 12px;

      p {
        font-family: "Noto Sans TC";
        font-size: 16px;
        font-weight: 400;
        margin-bottom: 16px
      }

      .symbol_box {
        li {
          display: flex;
          align-items: center;
          font-family: "Noto Sans TC";
          font-size: 16px;
          font-weight: 400;
          margin-bottom: 16px;
        }
      }

      .symbol {
        width: 32px;
        height: 32px;
        background-color: #030303;
        text-align: center;
        margin-right: 16px;
        line-height: 40px;
      }

    }

  }

}
</style>