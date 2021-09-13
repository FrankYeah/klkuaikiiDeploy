<template>
  <div class="index">
    <div class="index-video-box">
      <video playsinline autoplay muted loop>
        <!-- <source type="video/mp4" src="@/assets/video/monster-video.wmv"> -->
      </video>
    </div>

    <!-- 怪奇逃走中 -->
    <div class="index-intro">
      <div class="index-intro-head-box">
        <img class="index-intro-run-img" src="@/assets/img/index/text-main.png" alt="run">
        <img class="index-intro-run-img" src="@/assets/img/index/monster-hand.png" alt="hand">
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
    </div>

    <!-- 關於怪奇 -->
    <div class="index-about">
      <div class="index-about-box">
        <div class="index-about-text">是由無生命體演變而成，因累積過多人類情緒而產生意識，變成有生命體，如妖怪般的存在。每個怪奇之怪力皆不相同，怪力等級也因生成時累積的情緒而有所差異，目前基隆地區捕獲最強四大怪奇為旭川河、林開郡洋樓、委託行、通勤；一般人平時無法看見怪奇，唯有怪奇同類，或是觀察力異常細微之人才能看見。</div>
        <img class="index-about-img-hand" src="@/assets/img/index/monster-hand.png" alt="game">
        <div class="index-about-head">關於怪奇</div>
      </div>
    </div>

    <!-- 旭川與露露 -->
    <div class="index-role">
      <div class="index-role-box">
        <div class="index-role-img">
          <img src="@/assets/img/index/text-hunt.png" alt="hunt">
          <div class="index-role-text-box">
            <div class="index-role-head">旭川</div>
            <div class="index-role-text">危害等級：SSS</div>
            <div class="index-role-text">大約從1978年左右出沒在明德親民至善大樓，身上滿是漁網及腐臭魚屍，恐嚇人類會用沼氣炸掉大樓，造成當地居民恐慌，意圖不明。</div>
          </div>
        </div>
        <div class="index-role-img index-role-img-2">
          <img src="@/assets/img/index/text-hunt.png" alt="hunt">
          <div class="index-role-text-box">
            <div class="index-role-head">露露</div>
            <div class="index-role-text">危害等級：SSS</div>
            <div class="index-role-text">大約從基隆港口興盛的1960年前後出沒在委託行街區，擅長魅惑，跟其相關之失蹤人數已近百人。</div>
          </div>
        </div>
      </div>
    </div>


    <!-- 平行時空 -->
    <div class="index-pall">
      <div class="index-pall-text-box">
        <div class="index-pall-text"></div>
        <div class="index-pall-text"></div>
        <br>
        <div class="index-pall-text"></div>
        <div class="index-pall-text"></div>
        <br>
        <div class="index-pall-text"></div>
        <div class="index-pall-text"></div>
      </div>
      <img class="idnex-pall-img" src="@/assets/img/index/monster-bird.png" alt="bird">
    </div>


    <!-- 怪奇博物館 -->
    <div class="index-musium">
      <img class="index-musium-logo" src="@/assets/img/index/logo-black.png" alt="logo">
      <div class="index-musium-text-box">
        <div class="index-musium-text">「怪奇博物館」為世界公認研究、捕捉及管理怪奇之唯一官方組織,為防止怪奇危害人類、破壞環境,因此招集具有察覺怪奇能力之人,共同研究並擬定捕捉策略,將怪奇統一管理避免傷害,若有必要則進行銷毀怪奇之工作,維持人類世界之和平運作。</div>
        <div class="index-musium-text">組織總部設於英國倫敦,並於世界各地皆有分部,台灣分部自1960年起設於基隆港,因是地下秘密組織,原始核心成員又皆於任務中歿世,故確切成立時間已不可考。目前館長為第十五任Dr.張中元。</div>
      </div>
    </div>


    <!-- QA -->
    <div class="index-qa">

      <img class="index-musium-logo" src="@/assets/img/index/qa-btn.png" alt="qa">
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

      <br><br>
      <div class="index-qa-hint">若有其他問題，歡迎來信，</div>
      <div class="index-qa-hint">館員會盡快在雞籠曆許可的時間點回覆您，</div>
      <div class="index-qa-hint">若超過48小時未收到回信，</div>
      <div class="index-qa-hint">信件有極大可能被怪奇劫走，請再次與我們聯繫</div>
      <br>
      <div class="index-qa-hint">機密信箱：klkuaiki@gmail.com</div>
    </div>


    <!-- 團隊 -->
    <div class="index-team">
      <div class="index-team-box">
        <div class="index-team-head">怪奇團隊</div>
        <div class="index-team-line"></div>
        <div class="index-team-text-box">
          <div class="index-team-text">文安社區</div>
          <div class="index-team-text"></div>
          <div class="index-team-text">慾望劇團</div>
          <div class="index-team-text"></div>
          <div class="index-team-text">阿普蛙</div>
          <div class="index-team-text"></div>
          <div class="index-team-text">無用學堂</div>
          <div class="index-team-text"></div>
          <div class="index-team-text">西打藍</div>
          <div class="index-team-text"></div>
          <div class="index-team-text">叮叮咚咚</div>
        </div>
        <div class="index-team-icon-box">
          <div class="index-team-icon">f</div>
          <div class="index-team-icon">f</div>
          <div class="index-team-icon">W</div>
          <div class="index-team-icon">F</div>
          <div class="index-team-icon">W</div>
        </div>
      </div>

      <div class="index-team-feat">fEAT.</div>

      
      <div class="index-team-box">
        <div class="index-team-head">基隆市教育處</div>
        <div class="index-team-line"></div>
        <div class="index-team-text-box">
          <div class="index-team-text">學習型城市</div>
        </div>
        <div class="index-team-icon-box">
          <div class="index-team-icon">f</div>
          <div class="index-team-icon">W</div>
        </div>
      </div>
    </div>

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
  },
  props: {

  },
  data () {
    return {

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

}

@media( max-width: 500px ){

}

</style>
