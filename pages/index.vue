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
        >
          <source
            src="@/assets/video/monster-video.mp4"
            type="video/mp4"
          >
        </video>
      </div>
    </div>

    <!-- 怪奇逃走中 -->
    <contentBox class="index-intro">
      <div class="index-intro-head-box">
        <img class="index-intro-run-img" src="@/assets/img/index/text-main.png" alt="run">
        <img class="index-intro-hand-img" src="@/assets/img/index/monster-hand.png" alt="hand">
      </div>
      <div class="index-intro-text-box">
        <div class="index-intro-text-left">
          <div class="index-intro-text">混血實驗是轉機？或是衝突開端？</div>
          <div class="index-intro-text">究竟追尋真相重要？ 還是選擇重要？</div>
        </div>
        <div class="index-intro-text-right">
          <img class="index-intro-text-img" src="@/assets/img/index/text-game.png" alt="game">
          <div class="index-intro-text-green"># 120分鐘的實境解謎遊戲</div>
          <div class="index-intro-text-green"># 探討 3個議題</div>
          <div class="index-intro-text-green"># 體驗不一樣的思辨小旅行</div>
          <div class="index-intro-text-green"># 深度認識隱而不見的基隆</div>
        </div>
      </div>
       <router-link :to="'/about'" class="index-intro-about-box">
          <div class="index-intro-about">了解實驗</div>
       </router-link>
    </contentBox>

    <!-- 關於怪奇 -->
    <contentBox class="index-about">
      <div class="index-about-box">
        <div class="index-about-text">
          <div>是由無生命體演變而成，因累積過多人類情緒而產生意識，變成有生命體，如妖怪般的存在。每個怪奇之怪力皆不相同，怪力等級也因生成時累積的情緒而有所差異，目前基隆地區捕獲最強四大怪奇為旭川河、林開郡洋樓、委託行、通勤；一般人平時無法看見怪奇，唯有怪奇同類，或是觀察力異常細微之人才能看見。</div>
          
        </div>
        <img class="index-about-img-hand" src="@/assets/img/index/monster-hand.png" alt="game">
        <div class="index-about-head">關於怪奇</div>
      </div>
    </contentBox>

    <!-- 旭川與露露 -->
    <contentBox class="index-role">
      <div class="index-role-box">
        <div @mouseover="isShowCardText.river = true" @mouseleave="isShowCardText.river = false"
          class="index-role-img"
        >
          <img class="index-role-img-hunt" src="@/assets/img/index/text-hunt.png" alt="hunt">
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
        >
          <img class="index-role-img-hunt" src="@/assets/img/index/text-hunt.png" alt="hunt">
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
    <contentBox class="index-pall">
      <div class="index-pall-text-box">
        <div class="index-pall-text">一場平行時空的旅程</div>
        <div class="index-pall-text">這個路上你將會遇見誰</div>
        <br>
        <div class="index-pall-text">又看見什麼</div>
        <div class="index-pall-text">隱藏在這座城市的秘密</div>
        <br>
        <div class="index-pall-text">就等你開始探索</div>
        <div class="index-pall-text">你的真實身分</div>
      </div>
      <img class="index-pall-img" src="@/assets/img/index/monster-bird.png" alt="bird">
    </contentBox>


    <!-- 怪奇博物館 -->
    <contentBox class="index-musium">
      <div class="index-musium-box">
        <div class="index-musium-text-box">
          <div class="index-musium-text">「怪奇博物館」為世界公認研究、捕捉及管理怪奇之唯一官方組織,為防止怪奇危害人類、破壞環境,因此招集具有察覺怪奇能力之人,共同研究並擬定捕捉策略,將怪奇統一管理避免傷害,若有必要則進行銷毀怪奇之工作,維持人類世界之和平運作。</div>
          <div class="index-musium-text">組織總部設於英國倫敦,並於世界各地皆有分部,台灣分部自1960年起設於基隆港,因是地下秘密組織,原始核心成員又皆於任務中歿世,故確切成立時間已不可考。目前館長為第十五任Dr.張中元。</div>
        </div>
        <img class="index-musium-logo" src="@/assets/img/index/logo-black.png" alt="logo">
        <img class="index-musium-bg" src="@/assets/img/index/bg-blue-river.png" alt="river">
        
      </div>
    </contentBox>


    <!-- QA -->
    <contentBox class="index-qa">

      <div class="index-qa-box">

        <img class="index-qa-logo" src="@/assets/img/index/qa-btn.png" alt="qa">
        <div class="index-qa-question">．請問怪奇逃走中_混血探員在做甚麼？</div>
        <div class="index-qa-answer">。這是一個發生於基隆，手機結合街景的實境互動解謎。</div>
        
        <div class="index-qa-question">．如何得到探索身分？</div>
        <div class="index-qa-answer">。探員請注意，本次為機密任務，於2021年10月底前 (教育部確認)，僅為私下招募。預計於2022年年初擴大公開。</div>
        <div class="index-qa-answer">。信內包含：1.一份探員須知 / 2.四份探員序號(內部確認)。</div>
        
        <div class="index-qa-question">．探索總長度</div>
        <div class="index-qa-answer">。探索時間約2-3小時 / 建議探索時間10：00-17：00。(內部確認)</div>

        <div class="index-qa-question">．探索限制</div>
        <div class="index-qa-answer">。15歲以下探員，需成年探員陪同。</div>
        <div class="index-qa-answer">。由於搜捕怪奇穿梭於市區，包含上下樓等有障礙設備。行動不便者，為了維護您的安全，請探員慎重考慮。</div>
        
        <div class="index-qa-question">．退/換資訊</div>
        <div class="index-qa-answer">。無法參與的探員，建議將探員序號，轉給親友探索。</div>
        <div class="index-qa-answer">。如需退票的探員，請依照教育部的規則辦理。(教育部確認)</div>

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
              <div>地方活動設計</div>
              <br>
              <div>無用是一種精神，而學堂只是延伸</div>
              <br>
              <div>在這個以雨為名的城市，發起無數溫暖的地方生活實驗</div>
            </div>
            <div class="index-team-text-inner">
              <div>文安社區</div>
               <a class="index-team-icon" href="https://www.facebook.com/%E6%88%80%E6%88%80%E6%96%87%E5%AE%89-%E5%9F%BA%E9%9A%86%E6%96%87%E5%AE%89%E7%A4%BE%E5%8D%80-408355896023365" target="_blank">f</a>
            </div>
          </div>
          <div class="index-team-text">+</div>
          <div @mouseover="isShowDesc.youwant = true" @mouseleave="isShowDesc.youwant = false"
            class="index-team-text"
          >
            <div v-if="isShowDesc.youwant" class="index-team-popup">
              <div>慾望劇團</div>
              <br>
              <div>地方活動設計</div>
              <br>
              <div>無用是一種精神，而學堂只是延伸</div>
              <br>
              <div>在這個以雨為名的城市，發起無數溫暖的地方生活實驗</div>
            </div>
            <div class="index-team-text-inner">
              <div>慾望劇團</div>
              <a class="index-team-icon" href="https://www.facebook.com/desiretroupe" target="_blank">f</a>
            </div>
          </div>
          <div class="index-team-text">+</div>
          <div @mouseover="isShowDesc.frog = true" @mouseleave="isShowDesc.frog = false"
            class="index-team-text"
          >
            <div v-if="isShowDesc.frog" class="index-team-popup">
              <div>阿普蛙</div>
              <br>
              <div>地方活動設計</div>
              <br>
              <div>無用是一種精神，而學堂只是延伸</div>
              <br>
              <div>在這個以雨為名的城市，發起無數溫暖的地方生活實驗</div>
            </div>
            <div class="index-team-text-inner">
              <div>阿普蛙</div>
               <a class="index-team-icon" href="https://www.wasupstudio.com/" target="_blank">W</a>
            </div>
          </div>
          <div class="index-team-text">+</div>
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
          <div class="index-team-text">+</div>
          <div @mouseover="isShowDesc.siddharam = true" @mouseleave="isShowDesc.siddharam = false"
            class="index-team-text"
          >
            <div v-if="isShowDesc.siddharam" class="index-team-popup">
              <div>西打藍</div>
              <br>
              <div>地方活動設計</div>
              <br>
              <div>無用是一種精神，而學堂只是延伸</div>
              <br>
              <div>在這個以雨為名的城市，發起無數溫暖的地方生活實驗</div>
            </div>
            <div class="index-team-text-inner">
              <div>西打藍</div>
              <a class="index-team-icon" href="https://siddharam.com.tw/" target="_blank">W</a>
            </div>
          </div>
          <div class="index-team-text">+</div>
          <div @mouseover="isShowDesc.ding = true" @mouseleave="isShowDesc.ding = false"
            class="index-team-text"
          >
            <div v-if="isShowDesc.ding" class="index-team-popup">
              <div>叮叮咚咚</div>
              <br>
              <div>地方活動設計</div>
              <br>
              <div>無用是一種精神，而學堂只是延伸</div>
              <br>
              <div>在這個以雨為名的城市，發起無數溫暖的地方生活實驗</div>
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
              <div>地方活動設計</div>
              <br>
              <div>無用是一種精神，而學堂只是延伸</div>
              <br>
              <div>在這個以雨為名的城市，發起無數溫暖的地方生活實驗</div>
            </div>
            <div class="index-team-text-inner">
              <div>學習型城市</div>
              <div class="index-team-icon-box">
                <div class="index-team-icon">f</div>
                <div class="index-team-icon">W</div>
              </div>
            </div>
          </div>
        </div>
        
      </div>
    </contentBox>

    <!-- footer -->
    <bottomBar/>

  </div>
</template>

<script>

export default {
  head: {
    title: '首頁',
  },
  layout: 'default',
  components: {
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
    
  },
  computed: {

  },
  methods: {
    
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
    height: 100vh;
    
    &-box {
      width: 100%;
      height: 100vh;
    }
  }

  &-intro {
    margin-top: -1px;
    background: url('../assets/img/index/bg-blue.png');
    background-repeat: no-repeat;
    background-size: cover;
    background-position-x: center;
    background-position-y: center;
    background-attachment: fixed;

    &-head-box {
      display: flex;
      justify-content: center;
      align-items: center;
    }

    &-run-img {
      width: 400px;
    }

    &-hand-img {
      width: 500px;
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
      font-size: 22px;
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
      background: url('../assets/img/index/bg-blue-river.png');
      background-repeat: no-repeat;
      background-size: cover;
      background-position-x: center;
      background-position-y: center;
      width: 600px;
      height: 600px;
      line-height: 2;
      margin-right: 100px;
      font-size: 20px;
      color: white;
      z-index: 2;

      & div {
        width: 300px;
        transform: translateX(-18px);
      }
    }

    &-img-hand {
      width: 500px;
      position: absolute;
      top: 50px;
      right: 10%;
      transform: rotate(-30deg);
      z-index: 1;
    }

    &-head {
      font-size: 28px;
      color: #190140;
    }
  }

  &-role {
    background: url('../assets/img/index/bg-main.png');
    background-repeat: no-repeat;
    background-size: cover;
    background-position-x: center;
    background-position-y: center;
    background-attachment: fixed;

    &-box {
      display: flex;
      justify-content: center;
    }

    &-img {
      position: relative;
      width: 350px;
      height: 500px;
      margin: 0px 30px;
      background-image: url('../assets/img/index/monster-river.png');
      background-repeat: no-repeat;
      background-size: cover;
      background-position-x: center;
      background-position-y: center;
    }

    &-img:last-child {
      background-image: url('../assets/img/index/monster-lulu.png');
    
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
      font-size: 30px;
    }

    &-text {
      margin-top: 20px;
      line-height: 1.6;
    }
  }

  &-pall {
    position: relative;
    min-height: 600px;
    background: url('../assets/img/index/pic-scene.png');
    background-repeat: no-repeat;
    background-size: cover;
    background-position-x: center;
    background-position-y: center;
    background-attachment: fixed;

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
      width: 500px;
      height: 500px;
      background-repeat: no-repeat;
      background-size: cover;
      background-position-x: center;
      background-position-y: center;
      transform: rotate(200deg);
    }

    &-text-box {
      position: absolute;
      right: 60px;
      width: 344px;
      line-height: 2;
      font-size: 20px;
      color: white;
      z-index: 1;
    }

    &-text {
      font-size: 16px;
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
      bottom: 28px;
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

@media( max-width: 1023px ){

.index {

  &-video {
    height: auto;
    
    &-box {
      height: auto;
    }
  }

  &-intro {
    

    &-head-box {
      flex-direction: column;
    }

    &-run-img {
      width: 280px;
    }

    &-hand-img {
      width: 240px;
    }

    &-text-box {
      flex-direction: column;
    }

    &-text-left {
      margin: 0px;
      text-align: center;
    }

    &-text {
      
    }

    &-text-right {
      margin-top: 20px;
      text-align: center;
    }

    &-text-img {

    }

    &-text-green {
      
    }

    &-about-box {
      
    }

    &-about {
      margin: 30px auto 0px;
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
        font-size: 14px;
      }
    }

    &-img-hand {
      width: 240px;
      top: -114px;
      right: 10%;
      transform: rotate(-30deg);
    }

    &-head {
      margin-bottom: 20px;
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
      left: 20px;
      width: 250px;
      padding: 20px 6px;
    }

    &-head {
      
    }

    &-text {
      
    }
  }

  &-pall {
    min-height: 500px;

    &-text-box {
      
    }

    &-text {
      
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
      font-size: 14px;
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
      
    }

    &-answer {
      font-size: 14px;
    }

    &-hint {
      font-size: 14px;
      text-align: center;
    }
  }
  
  &-team {
    flex-wrap: wrap;

    &-box {
      

      &:first-child {

        & .index-team-icon-box {
          
        }

        & .index-team-icon {
          
        }
      }

      &:last-child {
        

        & .index-team-text-inner div {
          width: auto;
          height: 20px;
          margin-bottom: 10px;
        }

        & .index-team-icon {
          
        }
      }
    }

    &-head {
      font-size: 24px;
    }

    &-line {
      margin: 12px 0px;
    }

    &-text-box {
      
    }

    &-text {
      font-size: 14px;

      &:nth-child(1) .index-team-popup {
        left: 0px;
      }

      &:nth-child(3) .index-team-popup {
        left: -40px;
      }

      &:nth-child(5) .index-team-popup {
        left: -80px;
      }

      &:nth-child(7) .index-team-popup {
        left: -130px;
      }

      &:nth-child(9) .index-team-popup {
        left: -160px;
      }

      &:nth-child(11) .index-team-popup {
        left: -200px;
      }
    }

    &-text-inner {
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;

      & div {
        height: 60px;
        width: 20px;
      }
    }

    &-icon-box {
      
    }

    &-icon {
      font-size: 24px;
    }

    &-popup {
      bottom: 115px;
      padding: 10px;
      font-size: 14px;
      left: 20px;

      & div {
        
      }
    }

    &-popup-city {
      left: -50px !important;
    }

    &-feat {
      width: 100%;
      margin: 20px 0px;
      font-size: 16px;
      text-align: center;
    }
  }

}

}

</style>
