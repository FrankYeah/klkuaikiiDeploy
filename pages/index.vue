<template>
  <div class="index">
    <div class="index-video">
      <div class="index-video-box">
        <video
          width="100%"
          height="100%"
          autoplay
          loop
          muted
          playsinline
        >
          <source
            src="@/assets/video/monster-video.mp4"
            type="video/mp4"
          >
        </video>
      </div>
    </div>

    <!-- 怪奇逃走中 -->
    <contentBox ref="top" v-lazy:background-image="require('@/assets/img/index/bg-blue.png')" class="index-intro">
      <div class="index-intro-head-box">
        <img class="index-intro-run-img wow animate__fadeInRight" v-lazy="require('@/assets/img/index/text-main.png')" alt="run"
          data-wow-duration="1s"
          data-wow-delay="0s"
          data-wow-iteration="1"
        
        >
        <div class="index-intro-hand-img wow animate__fadeInTopLeft"
          data-wow-duration="2s"
          data-wow-delay="s"
          data-wow-iteration="1"
        ></div>
      </div>
      <div class="index-intro-text-box">
        <div class="index-intro-text-left wow animate__fadeIn"
          data-wow-duration="1s"
          data-wow-delay="0s"
          data-wow-iteration="1"
        >
          <div @click="scrollToRef()" class="index-intro-text">混血實驗是轉機？或是衝突開端？</div>
          <div class="index-intro-text">究竟追尋真相重要？ 還是選擇重要？</div>
        </div>
        <div class="index-intro-text-right">
          <img class="index-intro-text-img" v-lazy="require('@/assets/img/index/text-game.png')" alt="game">
          <div class="index-intro-text-green"># 120分鐘的實境解謎遊戲</div>
          <div class="index-intro-text-green"># 探討3個議題</div>
          <div class="index-intro-text-green"># 體驗不一樣的思辨小旅行</div>
          <div class="index-intro-text-green"># 深度認識隱而不見的基隆</div>
        </div>
      </div>
       <router-link :to="'/about'" class="index-intro-about-box">
          <div class="index-intro-about">了解實驗</div>
       </router-link>
    </contentBox>

    <!-- 關於怪奇 -->
    <contentBox ref="about" class="index-about">
      <div class="index-about-box">
        <div class="index-about-text"
          v-lazy:background-image="require('@/assets/img/index/bg-blue-river.png')"
        >
          <div>是由無生命體演變而成，因累積過多人類情緒而產生意識，變成有生命體，如妖怪般的存在。每個怪奇之怪力皆不相同，怪力等級也因生成時累積的情緒而有所差異，目前基隆地區捕獲最強四大怪奇為旭川河、林開郡洋樓、委託行、通勤；一般人平時無法看見怪奇，唯有怪奇同類，或是觀察力異常細微之人才能看見。</div>
          
        </div>
        <div class="index-about-img-hand wow animate__fadeInBottomLeft"
          data-wow-duration="1s"
          data-wow-delay="0s"
          data-wow-iteration="1"
        ></div>
        <!-- <img src="@/assets/img/index/monster-hand.png" alt="game"> -->
        <div class="index-about-head">關於怪奇</div>
      </div>
    </contentBox>

    <!-- 旭川與露露 -->
    <contentBox ref="run" class="index-role"
      v-lazy:background-image="require('@/assets/img/index/bg-main.png')"
    >
      <div class="index-role-box">
        <div @mouseover="isShowCardText.river = true" @mouseleave="isShowCardText.river = false"
          class="index-role-img"
          v-lazy:background-image="require('@/assets/img/index/monster-river.png')"
        >
          <img class="index-role-img-hunt wow animate__flipInX"
            src="@/assets/img/index/text-hunt.png" alt="hunt"
            data-wow-duration="1s"
            data-wow-delay="0s"
            data-wow-iteration="1"
          >
          <transition name="fade">
            <div v-if="isShowCardText.river" class="index-role-text-box">
              <div class="index-role-head">旭川</div>
              <div class="index-role-text">危害等級：SSS</div>
              <div class="index-role-text">大約從1978年左右出沒在明德親民至善大樓，身上滿是漁網及腐臭魚屍，恐嚇人類會用沼氣炸掉大樓，造成當地居民恐慌，意圖不明。</div>
            </div>
          </transition>
        </div>
        <div @mouseover="isShowCardText.lulu = true" @mouseleave="isShowCardText.lulu = false"
          class="index-role-img index-role-img-2"
          v-lazy:background-image="require('@/assets/img/index/monster-lulu.png')"
        >
          <img class="index-role-img-hunt wow animate__flipInX"
            src="@/assets/img/index/text-hunt.png" alt="hunt"
            data-wow-duration="1s"
            data-wow-delay="0s"
            data-wow-iteration="1"
          >
          <transition name="fade">
            <div v-if="isShowCardText.lulu" class="index-role-text-box">
              <div class="index-role-head">露露</div>
              <div class="index-role-text">危害等級：SSS</div>
              <div class="index-role-text">大約從基隆港口興盛的1960年前後出沒在委託行街區，擅長魅惑，跟其相關之失蹤人數已近百人。</div>
            </div>
          </transition>
        </div>
      </div>
    </contentBox>


    <!-- 平行時空 -->
    <contentBox ref="time" class="index-pall"
    >
      <div class="index-pall-text-box">
        <div class="index-pall-text wow animate__fadeIn"
          data-wow-duration="1s"
          data-wow-delay="0s"
          data-wow-iteration="1"
        >一場平行時空的旅程</div>
        <div class="index-pall-text wow animate__fadeIn"
          data-wow-duration="3s"
          data-wow-delay="0s"
          data-wow-iteration="1"
        >這個路上你將會遇見誰</div>
        <br>
        <div class="index-pall-text wow animate__fadeIn"
          data-wow-duration="5s"
          data-wow-delay="0s"
          data-wow-iteration="1"
        >又看見什麼</div>
        <div class="index-pall-text wow animate__fadeIn"
          data-wow-duration="7s"
          data-wow-delay="0s"
          data-wow-iteration="1"
        >隱藏在這座城市的秘密</div>
        <br>
        <div class="index-pall-text wow animate__fadeIn"
          data-wow-duration="9s"
          data-wow-delay="0s"
          data-wow-iteration="1"
        >就等你開始探索</div>
        <div class="index-pall-text wow animate__fadeIn"
          data-wow-duration="11s"
          data-wow-delay="0s"
          data-wow-iteration="1"
        >你的真實身分</div>
      </div>
      <a href="https://frankyeah.github.io/klkuaiki/index.html" target="_blank">
        <img class="index-pall-img wow animate__rubberBand" v-lazy="require('@/assets/img/index/monster-bird.png')" alt="bird"
          data-wow-duration="1s"
          data-wow-delay="0s"
          data-wow-iteration="infinite"
        >
      </a>
    </contentBox>


    <!-- 怪奇博物館 -->
    <contentBox ref="musium" class="index-musium">
      <div class="index-musium-box">
        <div class="index-musium-text-box wow animate__fadeIn"
          data-wow-duration="1s"
          data-wow-delay="0s"
          data-wow-iteration="1"
        >
          <div class="index-musium-text">世界各地皆有怪奇組織,台灣的怪奇官方組織為「怪奇博物館」。據傳本館設於基隆港,因是地下秘密組織,原始核心成員又皆於任務中歿世,故確切成立時間已不可考。目前館長為第十五任Dr.張中元。</div>
          <div class="index-musium-text">「怪奇博物館」為研究、捕捉及管理怪奇之組織,為防止怪奇危害人類、破壞環境,因此招集具有察覺怪奇能力之人,共同研究並擬定捕捉策略,將怪奇統一管理避免傷害,若有必要則進行銷毀怪奇之工作,維持人類世界之和平運作。</div>
        </div>
        <img class="index-musium-logo" v-lazy="require('@/assets/img/index/logo-black.png')" alt="logo">
        <img class="index-musium-bg" v-lazy="require('@/assets/img/index/bg-blue-river.png')" alt="river">
        
      </div>
    </contentBox>


    <!-- QA -->
    <contentBox ref="qa" class="index-qa">

      <div class="index-qa-box">

        <img class="index-qa-logo" v-lazy="require('@/assets/img/index/qa-btn.png')" alt="qa">
        <div class="index-qa-question">．請問怪奇逃走中_混血探員在做什麼？</div>
        <div class="index-qa-answer">。這是一個發生於基隆，手機結合街景的實境互動解謎遊戲。</div>
        
        <div class="index-qa-question">．如何得到探員身分？</div>
        <div class="index-qa-answer">。本次為極機密任務。於2021年12月底前，由教育處私下招募探員，每位探員將有專屬登入序號。</div>
        <div class="index-qa-answer">。想自告奮勇成為探員嗎？請洽招募窗口：（教育處窗口）</div>
        
        <div class="index-qa-question">．探索時間</div>
        <div class="index-qa-answer">。探索時間約2-3小時 / 建議探索時間10：00-17：00。</div>

        <div class="index-qa-question">．探索限制</div>
        <div class="index-qa-answer">。15歲以下探員，需成年探員陪同。</div>
        <div class="index-qa-answer">。搜捕怪奇穿梭於雞籠市區，包含上下樓等有障礙設備。</div>
        <div class="index-qa-answer">。手機全程需使用網路，遊戲內含影音，為求最佳體驗，請自備耳機。</div>
        
        <!-- <div class="index-qa-question">．退/換資訊</div>
        <div class="index-qa-answer">。無法參與的探員，建議將探員序號，轉給親友探索。</div>
        <div class="index-qa-answer">。如需退票的探員，請依照教育部的規則辦理。(教育部確認)</div> -->

        <br><br><br><br>
        <div class="index-qa-hint">若有其他問題，歡迎來信，</div>
        <div class="index-qa-hint">館員會盡快在雞籠曆許可的時間點回覆您，</div>
        <div class="index-qa-hint">若超過48小時未收到回信，</div>
        <div class="index-qa-hint">信件有極大可能被怪奇劫走，請再次與我們聯繫</div>
        <br>
        <div class="index-qa-hint">機密信箱：klkuaiki@gmail.com</div>

      </div>
    </contentBox>


    <!-- 團隊 -->
    <contentBox class="index-team">
      <div class="index-team-box">
        <div class="index-team-head">怪奇團隊</div>
        <div class="index-team-line"></div>
        <div class="index-team-text-box">
          <div @mouseover="isShowDesc.community = true" @mouseleave="isShowDesc.community = false"
            class="index-team-text"
          >
            <div v-if="isShowDesc.community" class="index-team-popup">
              <div>文安社區</div>
              <br>
              <div>座落市區的古老社區，也是基隆社造的元老級社區。</div>
              <br>
              <div>以文史帶領居民認同在地、以多元串連地方資源整合、以社區跨出社區的社造想像。</div>
            </div>
            <div class="index-team-text-inner">
              <div>文安社區</div>
               <a class="index-team-icon" href="https://www.facebook.com/%E6%88%80%E6%88%80%E6%96%87%E5%AE%89-%E5%9F%BA%E9%9A%86%E6%96%87%E5%AE%89%E7%A4%BE%E5%8D%80-408355896023365" target="_blank">f</a>
            </div>
          </div>
          <div class="index-team-text index-team-plus">+</div>
          <div @mouseover="isShowDesc.youwant = true" @mouseleave="isShowDesc.youwant = false"
            class="index-team-text"
          >
            <div v-if="isShowDesc.youwant" class="index-team-popup">
              <div>慾望劇團</div>
              <br>
              <div>基隆在地劇團</div>
              <br>
              <div>擅長挖掘在地故事並改編成戲劇演出</div>
              <br>
              <div>「透過戲劇拉近人與人之間的距離，並傳達愛與感動。」</div>
            </div>
            <div class="index-team-text-inner">
              <div>慾望劇團</div>
              <a class="index-team-icon" href="https://www.facebook.com/desiretroupe" target="_blank">f</a>
            </div>
          </div>
          <div class="index-team-text index-team-none">+</div>
          <div @mouseover="isShowDesc.frog = true" @mouseleave="isShowDesc.frog = false"
            class="index-team-text"
          >
            <div v-if="isShowDesc.frog" class="index-team-popup">
              <div>阿普蛙</div>
              <br>
              <div>基隆在地社企</div>
              <br>
              <div>希望透過遊戲的方式讓人認識社會議題，</div>
              <br>
              <div>推廣公民教育，為社會帶來正面的影響力。</div>
            </div>
            <div class="index-team-text-inner">
              <div>阿普蛙</div>
               <a class="index-team-icon" href="https://www.wasupstudio.com/" target="_blank">W</a>
            </div>
          </div>
          <div class="index-team-text index-team-plus">+</div>
          <div @mouseover="isShowDesc.use = true" @mouseleave="isShowDesc.use = false"
            class="index-team-text"
          >
            <div v-if="isShowDesc.use" class="index-team-popup">
              <div>無用學堂</div>
              <br>
              <div>地方活動設計</div>
              <br>
              <div>無用是一種精神，而學堂只是延伸</div>
              <br>
              <div>在這個以雨為名的城市，發起無數溫暖的地方生活實驗</div>
            </div>
            <div class="index-team-text-inner">
              <div>無用學堂</div>
              <a class="index-team-icon" href="https://www.facebook.com/KeelungLifeLab" target="_blank">F</a>
            </div>
          </div>
          <div class="index-team-text index-team-none">+</div>
          <div @mouseover="isShowDesc.siddharam = true" @mouseleave="isShowDesc.siddharam = false"
            class="index-team-text"
          >
            <div v-if="isShowDesc.siddharam" class="index-team-popup">
              <div>西打藍</div>
              <br>
              <div>寫程式的文字人</div>
              <br>
              <div>記者、前端工程師、自由工作者</div>
              <br>
              <div>以基隆為根、愛好思考，實現各式生活的多棲人生</div>
            </div>
            <div class="index-team-text-inner">
              <div>西打藍</div>
              <a class="index-team-icon" href="https://siddharam.com.tw/" target="_blank">W</a>
            </div>
          </div>
          <div class="index-team-text index-team-plus">+</div>
          <div @mouseover="isShowDesc.ding = true" @mouseleave="isShowDesc.ding = false"
            class="index-team-text"
          >
            <div v-if="isShowDesc.ding" class="index-team-popup">
              <div>叮叮咚咚</div>
              <br>
              <div>一個地球人類。正在練習自己內在跟外在的平衡</div>
              <br>
              <div>觀察自己觀察世界，在這世界玩～</div>
            </div>
            <div class="index-team-text-inner">
              <div>叮叮咚咚</div>
            </div>
          </div>
        </div>
      </div>

      <div class="index-team-feat">FEAT.</div>

      <div class="index-team-box">
        <div class="index-team-head">基隆市教育處</div>
        <div class="index-team-line"></div>
        <div class="index-team-text-box">
          <div @mouseover="isShowDesc.education = true" @mouseleave="isShowDesc.education = false"
            class="index-team-text"
          >
            <div v-if="isShowDesc.education" class="index-team-popup index-team-popup-city">
              <div></div>
              <br>
              <div>以「多元聯盟、跨域共榮」為主軸，</div>
              <br>
              <div>形塑文創意象、凝聚社區共識、推動觀光體驗，</div>
              <br>
              <div>並嘗試接軌國際，從地方創生回應全球挑戰。</div>
            </div>
            <div class="index-team-text-inner">
              <div>學習型城市</div>
              <div class="index-team-icon-box">
                <a class="index-team-icon" href="https://www.facebook.com/klcg.gov.tw/" target="_blank">f</a>
              </div>
            </div>
          </div>
        </div>
        
      </div>
    </contentBox>

    <!-- footer -->
    <bottomBar/>
    <!-- sidebar -->
    <sideBar @scrollToRefs="scrollToRef" />
    <!-- topbar -->
    <topBar @scrollToRefs="scrollToRef" />

  </div>
</template>

<script>

if (process.browser) { // Here we introduce... According to the environment wow.js
  var {WOW} = require('wowjs')
}

export default {
  head: {
    title: '怪奇逃走中-混血探員',
  },
  layout: 'default',
  components: {
    topBar: require('~/components/top-bar.vue').default, 
    sideBar: require('~/components/side-bar.vue').default, 
    bottomBar: require('~/components/bottom-bar.vue').default, 
    contentBox: require('~/components/content-box.vue').default, 
  },
  props: {

  },
  data () {
    return {
      isShowCardText: {
        river: false,
        lulu: false
      },
      isShowDesc: {
        community: false,
        youwant: false,
        frog: false,
        use: false,
        siddharam: false,
        ding: false,
        education: false
      }
    }
  },
  mounted () {
    var mediaElem = document.querySelector("video")
    mediaElem.load()

    // wow
    this.$nextTick(() => {
      if (process.browser) { // On the page mounted In the life cycle Instantiate according to the environment WOW
        new WOW({
          boxClass: 'wow', // 欲套用wow.js的class
          animateClass: 'animated', // 欲修改設定animat.css 的類別名稱
          offset: 0, // 當用戶滾動並到達這個距離時才開始執行動畫
          mobile: true, // 是否在行動裝置上執行動畫
          live: false, // 非同步產生的內容是否要套用
          callback: null,
          scrollContainer: null
        }).init()
      }
    })
  },
  computed: {

  },
  methods: {
    scrollToRef(id) {
      this.$nextTick(() => {
        this.$refs[id].$el.scrollIntoView({ behavior: 'smooth' })
      })
    }
  },
  watch: {
    
  }
}
</script>

<style lang="scss" scoped>

.index {

  &-video {
    background-color: rgb(17, 17, 82);
    position: relative;
    width: 100%;
    height: 100%;
    
    &-box {
      width: 100%;
      height: 100%;
    }
  }

  &-intro {
    position: relative;
    margin-top: -1px;
    background-repeat: no-repeat;
    background-size: cover;
    background-position-x: center;
    background-position-y: center;

    &-head-box {
      display: flex;
      justify-content: flex-end;
      align-items: center;
    }

    &-run-img {
      width: 30vw;
    }

    &-hand-img {
      background-image: url('../assets/img/index/monster-hand.png');
      background-repeat: no-repeat;
      background-size: cover;
      background-position-x: center;
      background-position-y: center;
      width: 660px;
      height: 330px;
      transform: rotate(20deg) scaleX(-1);
    }

    &-text-box {
      margin: 20px 0px 0px;
      display: flex;
      justify-content: center;
    }

    &-text-left {
      margin-right: 50px;
    }

    &-text {
      margin-top: 10px;
      font-size: 17px;
    }

    &-text-right {

    }

    &-text-img {

    }

    &-text-green {
      margin-top: 10px;
      color: #96ff3c;
    }

    &-about-box {
      margin: 50px 0px;
    }

    &-about {
      width: 100px;
      height: 40px;
      margin: 50px auto 0px;
      line-height: 40px;
      text-align: center;
      border-radius: 20px;
      color: rgb(17, 17, 82);
      background-color: #96ff3c;
      cursor: pointer;

      &:hover {
        color: #96ff3c;
        background-color: rgb(17, 17, 82);
      }
    }

  }
  
  &-about {
    background: linear-gradient(to right bottom, rgb(194, 246, 185) 14px, rgb(37, 224, 4) 87%, rgb(37, 224, 4));

    &-box {
      position: relative;
      display: flex;
      justify-content: center;
      align-items: center;
    }

    &-text {
      display: flex;
      justify-content: center;
      align-items: center;
      background-repeat: no-repeat;
      background-size: cover;
      background-position-x: center;
      background-position-y: center;
      width: 600px;
      height: 600px;
      line-height: 2;
      margin-right: 100px;
      font-size: 19px;
      color: white;
      z-index: 2;

      & div {
        width: 300px;
        transform: translateX(-18px);
      }
    }

    &-img-hand {
      width: 500px;
      height: 200px;
      position: absolute;
      top: 50px;
      right: calc(45% - 403px);
      background-image: url('../assets/img/index/monster-hand.png');
      background-repeat: no-repeat;
      background-size: cover;
      background-position-x: center;
      background-position-y: center;
      transform: rotate(-30deg);
      pointer-events: none;
      z-index: 1;
    }

    &-head {
      font-size: 28px;
      color: #190140;
    }
  }

  &-role {
    position: relative;
    background-repeat: no-repeat;
    background-size: cover;
    background-position-x: center;
    background-position-y: center;

    &-box {
      display: flex;
      justify-content: center;
    }

    &-img {
      position: relative;
      width: 350px;
      height: 500px;
      margin: 0px 30px;
      background-repeat: no-repeat;
      background-size: cover;
      background-position-x: center;
      background-position-y: center;
    }

    &-img:last-child {
    
      & img {
        transform: rotate(-16deg) translate(-34px, -43px);
      }
    }

    &-img-hunt {
      width: 140px;
      transform: rotate(36deg) translate(-10px, 38px);
    }

    &-text-box {
      position: absolute;
      bottom: 20px;
      left: 34px;
      width: 260px;
      margin: auto;
      padding: 20px 10px;
      color: white;
      background-color: rgba(0, 0, 0, 0.4);
    }

    &-head {
      font-size: 22px;
    }

    &-text {
      margin-top: 20px;
      font-size: 17px;
      line-height: 1.6;
    }
  }

  &-pall {
    position: relative;
    height: 600px;

    &::before {
      content: ' ';
      position: fixed;
      z-index: -1;
      top: 0;
      right: 0;
      bottom: 0;
      left: 0;
      background-image: url('../assets/img/index/pic-scene.jpg');
      background-repeat: no-repeat;
      background-size: cover;
      background-position-x: center;
      background-position-y: bottom;
    }

    &-text-box {
      position: absolute;
      right: 20%;
      writing-mode: vertical-rl;
    }

    &-text {
      margin-left: 10px;
      font-size: 20px;
    }

    &-img {
      position: absolute;
      left: 15%;
      bottom: 50px;
      width: 100px;

      &:hover {
        opacity: 0.8;
      }
    }
  }


  &-musium {
    display: flex;
    align-items: center;
    justify-content: center;
    background-color: #25e004;

    &-box {
      position: relative;
      display: flex;
      align-items: center;
      justify-content: center;
    }

    &-logo {
      width: 140px;
    }

    &-bg {
      width: 568px;
      height: 660px;
      background-repeat: no-repeat;
      background-size: cover;
      background-position-x: center;
      background-position-y: center;
      transform: rotate(200deg);
    }

    &-text-box {
      position: absolute;
      right: 60px;
      width: 410px;
      line-height: 2;
      font-size: 20px;
      color: white;
      z-index: 1;
    }

    &-text {
      font-size: 19px;
      margin: 20px 0px;
    }
  }


  &-qa {
    background-color: #190140;

    &-box {
      width: 700px;
      margin: auto;
    }

    &-logo {
      width: 80px;
    }

    &-question {
      margin: 30px 0px 8px;
      color: #25e004;
    }

    &-answer {
      line-height: 1.5;
      text-indent: -16px;
      margin-left: 16px;
    }

    &-hint {
      margin-top: 6px;
      color: #25e004;
    }
  }
  
  &-team {
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: #25e004;
    color: #190140;

    &-box {
      width: 600px;

      &:first-child {

        & .index-team-icon-box {
          
        }

      }

      &:last-child {
        width: 200px;

        & .index-team-icon-box {
          justify-content: center;
        }

        & .index-team-icon {
          margin: 0px 10px;
        }
      }
    }

    &-head {
      font-size: 28px;
      text-align: center;
    }

    &-line {
      height: 1px;
      margin: 24px 0px;
      background-color: #190140;
    }

    &-text-box {
      display: flex;
      justify-content: center;
      text-align: center;
    }

    &-text {
      position: relative;
      margin: 0px 4px;
      font-size: 20px;

      &:hover {
        color: rgba(25, 1, 64, 0.6);
      }
    }

    &-text-inner {
      
      & div:first-child {
        margin-bottom: 20px;
      }
    }

    &-icon-box {
      display: flex;
      justify-content: center;
    }

    &-icon {
      font-size: 32px;
      font-weight: bold;
      color: #190140;
    }

    &-popup {
      position: absolute;
      bottom: 90px;
      width: 200px;
      padding: 20px;
      color: white;
      background-color: rgba(0, 0, 0, 0.6);

      & div {
        line-height: 1.2;
      }
    }

    &-feat {
      margin: 0px 10px;
      font-size: 20px;
    }
  }

}

// ----------------------------------------------------

// ----------------------------------------------------

@media( max-width: 1023px ){

.index {
  margin-top: 49px;

  &-video {
    height: auto;
    
    &-box {
      height: auto;
    }
  }

  &-intro {
    padding: 40px 0px 30px;

    &-head-box {
      position: relative;
      justify-content: flex-start;
    }

    &-run-img {
      width: 250px;
      margin-left: 30px;
    }

    &-hand-img {
      position: absolute;
      top: -40px;
      right: 10px;
      width: 50vw;
      height: 100px;
      background-position-x: right;
      transform: rotate(10deg) scaleX(-1);
    }

    &-text-box {
      flex-direction: column;
    }

    &-text-left {
      width: 60%;
      margin: 40px auto;
    }

    &-text {
      line-height: 1.5;
    }

    &-text-right {
      margin: 20px auto;
      text-align: center;
    }

    &-text-img {
      margin-bottom: 20px;
    }

    &-text-green {
      font-size: 17px;
      text-align: left;
    }

    &-about-box {
      
    }

    &-about {
      margin: 20px auto;
    }

  }
  
  &-about {
    

    &-box {
      flex-direction: column-reverse;
    }

    &-text {
      background: none;
      width: auto;
      height: auto;
      margin: 0px;
      color: #111152;

      & div {
        transform: none;
        font-size: 17px;
      }
    }

    &-img-hand {
      width: 60vw;
      height: 100px;
      top: -32px;
      left: -40px;
      background-position-x: right;
      transform: rotate(-18deg);
    }

    &-head {
      width: 100%;
      margin: 30px 0px;
      font-size: 18px;
      text-align: right;
    }
  }

  &-role {
    

    &-box {
      flex-direction: column;
      align-items: center;
    }

    &-img {
      width: 300px;
      height: 460px;
      margin: 10px 0px;
    }

    &-img:last-child {
      
    
      & img {
        transform: rotate(-16deg) translate(-16px, 12px);
      }
    }

    &-img-hunt {
      width: 90px;
      transform: rotate(36deg) translate(-10px, 10px)
    }

    &-text-box {
      bottom: 0px;
      left: 0px;
      width: 288px;
      padding: 20px 6px;
    }

    &-head {
      
    }

    &-text {
      
    }
  }

  &-pall {
    height: 500px;

    &-text-box {
      
    }

    &-text {
      font-size: 17px;
    }

    &-img {
      
    }
  }


  &-musium {
    

    &-box {
      flex-direction: column-reverse;
    }

    &-logo {
      width: 100px;
    }

    &-bg {
      display: none;
      // width: 316px;
      // height: 316px;
      // transform: rotate(0deg);
    }

    &-text-box {
      position: initial;
      width: 95%;
    }

    &-text {
      margin: 20px 0px 0px;
      font-size: 17px;
      color: #111152;
    }
  }


  &-qa {
    

    &-box {
      width: 100%;
    }

    &-logo {
      width: 60px;
    }

    &-question {
      font-size: 17px;
    }

    &-answer {
      font-size: 17px;
    }

    &-hint {
      font-size: 17px;
      text-align: center;
    }
  }
  
  &-team {
    flex-direction: column;

    &-box {
      

      &:first-child {
        width: 100%;

        & .index-team-icon-box {
          
        }

        & .index-team-icon {
          
        }
      }

      &:last-child {
        width: 100%;

        & .index-team-text-inner div {
          
        }

        & .index-team-icon {
          
        }
      }
    }

    &-head {
      font-size: 19px;
    }

    &-line {
      margin: 14px 0px 40px;
    }

    &-text-box {
      flex-wrap: wrap;
    }

    &-text {
      width: 40%;
      margin-bottom: 40px;

      &:nth-child(1) .index-team-popup {
        
      }

      &:nth-child(3) .index-team-popup {
        right: 20px;
      }

      &:nth-child(5) .index-team-popup {
        
      }

      &:nth-child(7) .index-team-popup {
        right: 20px;
      }

      &:nth-child(9) .index-team-popup {
        
      }

      &:nth-child(11) .index-team-popup {
        right: 20px;
      }
    }

    &-plus {
      width: 10%;
    }

    &-none {
      display: none;
    }

    &-text-inner {
      font-size: 18px;

      & div:first-child {
        margin-bottom: 10px;
      }
      

      & div {
        
      }
    }

    &-icon-box {
      
    }

    &-icon {
      
    }

    &-popup {
      

      & div {
        font-size: 16px;
      }
    }

    &-popup-city {
      
    }

    &-feat {
      margin: 30px 0px 20px;
      font-size: 15px;
    }
  }

}

}

</style>
