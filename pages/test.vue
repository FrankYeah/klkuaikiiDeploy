<template>
  <div class="test">

    <!-- 前言 -->
    <div v-if="isShowResult == '前言'" class="test-pre">

      <img class="test-pre-img" src="@/assets/img/test/monster/fish.png" alt="fish">

      <div class="test-pre-text-box">
        <div class="test-pre-text"> 探員⋯⋯</div>
        <div class="test-pre-text">不，應該稱呼你為「怪奇」了。</div>
        <div class="test-pre-text">經過一番歷險的你，</div>
        <div class="test-pre-text">終於找回自己的真實身份。</div>
        <div class="test-pre-text">但你有想過自己是哪一隻怪奇嗎？</div>
        <br><br>
        <div class="test-pre-text">在這個人類主宰的世界裡，</div>
        <div class="test-pre-text">身為怪奇的你會怎麼做呢？</div>
        <div class="test-pre-text">回答下面這些問題，</div>
        <div class="test-pre-text">找出你是哪一隻怪奇。</div>
      </div>
      <div class="text-pre-start-box">
        <div class="test-pre-start" @click="isShowResult = '題目'">START</div>
      </div>
    </div>

    <!-- 回答問題 -->
    <div v-else-if="isShowResult == '題目'" class="test-qa">
      <div>
        <div class="test-qa-img-box">
          <div class="test-qa-num">{{qNum + 1}}.</div>
          <img class="test-qa-img" :src="require(`@/assets/img/test/monster/${qa[qNum].monster}.png`)" alt="monster">
        </div>
        <!-- require('@/assets/img/test/monster/fish.png') -->
        <div v-html="qa[qNum].question" class="test-qa-question"></div>
        <div @click="selectType(qa[qNum].ans1Type)" class="test-qa-answer">{{ qa[qNum].ans1 }}</div>
        <div @click="selectType(qa[qNum].ans2Type)" class="test-qa-answer">{{ qa[qNum].ans2 }}</div>
        <div @click="selectType(qa[qNum].ans3Type)" class="test-qa-answer">{{ qa[qNum].ans3 }}</div>
        <div @click="selectType(qa[qNum].ans4Type)" class="test-qa-answer">{{ qa[qNum].ans4 }}</div>
        <div @click="selectType(qa[qNum].ans5Type)" class="test-qa-answer">{{ qa[qNum].ans5 }}</div>
      </div>
    </div>

    <!-- 解答 -->
    <div v-else-if="isShowResult == '解答'" class="test-result">
      <img :class="['test-result-img', {'test-result-img-tall': resultImg == 'stop' || resultImg == 'cancer'}]" :src="require(`@/assets/img/test/monster/${resultImg}.png`)" alt="monster">
      <div class="test-result-text">你是</div>
      <div class="test-result-text-btn">{{ result }}</div>
      <img @click="isShowResult = '解說'" class="test-result-next" :src="require(`@/assets/img/test/next.png`)" alt="monster">
    </div>

    <!-- 解說 -->
    <div v-else-if="isShowResult == '解說'" class="test-desc">
      <img :src="require(`@/assets/img/test/monster/${resultImg}.png`)" alt="monster"
        :class="['test-desc-img',
          {'test-desc-img-small': resultImg == 'man' || resultImg == 'hole'},
          {'test-desc-img-smaller': resultImg == 'bridge'}
        ]"
      >
      <div class="test-desc-name">{{ result }}</div>
      <div class="test-desc-sub">特性</div>
      <div v-html="resultText[`${resultImg}`].reason" class="test-desc-text"></div>
      <div class="test-desc-desc">
        <div v-html="resultText[`${resultImg}`].desc"></div>
        <img @click="isShowResult = '再玩一次'" class="test-desc-next" :src="require(`@/assets/img/test/next.png`)" alt="monster">
      </div>
    </div>

    <!-- 再玩一次 -->
    <div v-else-if="isShowResult == '再玩一次'" class="test-re">
      <img v-if="!isShowMonster.hole" @mouseover="isShowMonster.hole = true" class="test-re-img" :src="require(`@/assets/img/test/monster/hole2.png`)" alt="bridge">
      <img v-else class="test-re-img" @mouseleave="isShowMonster.hole = false" @click="introMonster('hole')" :src="require(`@/assets/img/test/monster/hole.png`)" alt="bridge">
      
      <img v-if="!isShowMonster.stop" @mouseover="isShowMonster.stop = true" class="test-re-img" :src="require(`@/assets/img/test/monster/stop2.png`)" alt="stop">
      <img v-else class="test-re-img" @mouseleave="isShowMonster.stop = false" @click="introMonster('stop')" :src="require(`@/assets/img/test/monster/stop.png`)" alt="stop">
      
      <img v-if="!isShowMonster.bridge" @mouseover="isShowMonster.bridge = true" class="test-re-img" :src="require(`@/assets/img/test/monster/bridge2.png`)" alt="hole">
      <img v-else class="test-re-img" @mouseleave="isShowMonster.bridge = false" @click="introMonster('bridge')" :src="require(`@/assets/img/test/monster/bridge.png`)" alt="stop">
      
      <img v-if="!isShowMonster.cancer" @mouseover="isShowMonster.cancer = true" class="test-re-img" :src="require(`@/assets/img/test/monster/cancer2.png`)" alt="cancer">
      <img v-else class="test-re-img" @mouseleave="isShowMonster.cancer = false" @click="introMonster('cancer')" :src="require(`@/assets/img/test/monster/cancer.png`)" alt="stop">
      
      <img v-if="!isShowMonster.man" @mouseover="isShowMonster.man = true" class="test-re-img" :src="require(`@/assets/img/test/monster/man2.png`)" alt="man">
      <img v-else class="test-re-img" @mouseleave="isShowMonster.man = false" @click="introMonster('man')" :src="require(`@/assets/img/test/monster/man.png`)" alt="stop">
      
      <div v-if="isShowAgain" class="test-re-btn-box">
        <img @click="isShowResult = '前言'" class="test-re-return" :src="require(`@/assets/img/test/return.png`)" alt="monster">
        <div @click="isShowResult = '前言'" class="test-re-text">再玩一次</div>
        <div @click="isShowAgain = false" class="test-re-btn">認識其他小怪奇</div>
        <router-link :to="'/literacy'" class="test-re-btn">了解怪奇</router-link>
      </div>
    </div>

    
  </div>
</template>

<script>

export default {
  head: {
    title: '怪奇逃走中-混血探員',
  },
  layout: 'default',
  components: {

  },
  props: {

  },
  data () {
    return {
      qNum: 0,
      isShowResult: '前言',
      totalType: {
        naive: 0,
        orphan: 0,
        wonderer: 0,
        fighter: 0,
        sacre: 0
      },
      qa: [
        {
          monster: 'air2',
          question: '你怎麼看待<br>許多人類對你們怪奇的敵意？',
          ans1: 'A：一定是有什麼誤會。',
          ans1Type: 'naive',
          ans2: 'B：他們注定就是痛恨怪奇。',
          ans2Type: 'orphan',
          ans3: 'C：那又怎樣？不管他們就好。',
          ans3Type: 'wonderer',
          ans4: 'D：我會改變人類對我們的看法。',
          ans4Type: 'fighter',
          ans5: 'E：我不會讓怪奇受到傷害的。',
          ans5Type: 'sacre',
        },
        {
          monster: 'wallet',
          question: '面對人類持續不斷的追捕、迫害，你會怎麼反應？',
          ans1: 'A：戰鬥！',
          ans1Type: 'fighter',
          ans2: 'B：自我犧牲（來保護其他怪奇）。',
          ans2Type: 'sacre',
          ans3: 'C：嘗試與他們對話。',
          ans3Type: 'naive',
          ans4: 'D：徹底偽裝成人類。',
          ans4Type: 'orphan',
          ans5: 'E：到處流浪、閃躲。',
          ans5Type: 'wonderer',
        },
        {
          monster: 'lighter',
          question: '你怎麼看待<br>身邊千奇百怪的怪奇？',
          ans1: 'A：想跟他們維持好關係。',
          ans1Type: 'naive',
          ans2: 'B：他們跟人類，都很危險⋯⋯',
          ans2Type: 'orphan',
          ans3: 'C：他們需要我的協助。',
          ans3Type: 'sacre',
          ans4: 'D：我也有不輸給他們的能力。',
          ans4Type: 'fighter',
          ans5: 'E：很難與他們互相理解。',
          ans5Type: 'wonderer',
        },
        {
          monster: 'fish',
          question: '你擁有比其他怪奇更強大的能力<br>你會怎麼做？',
          ans1: 'A：保持低調，保護好自己。',
          ans1Type: 'orphan',
          ans2: 'B：為保護弱小怪奇而戰。',
          ans2Type: 'sacre',
          ans3: 'C：貢獻自身於怪奇、人類社會。',
          ans3Type: 'naive',
          ans4: 'D：去世界各處冒險。',
          ans4Type: 'wonderer',
          ans5: 'E：成為所有怪奇認同的領袖。',
          ans5Type: 'fighter',
        },
        {
          monster: 'air',
          question: '你會想對比你弱小的怪奇們<br>說些什麼？',
          ans1: 'A：要努力活下去。',
          ans1Type: 'fighter',
          ans2: 'B：保持樂觀，明天會更好的。',
          ans2Type: 'naive',
          ans3: 'C：我不會讓你們受傷害的。',
          ans3Type: 'sacre',
          ans4: 'D：生死有命，別太在意。',
          ans4Type: 'wonderer',
          ans5: 'E：其實我也有脆弱的一面⋯⋯',
          ans5Type: 'orphan',
        },
        {
          monster: 'air',
          question: '你認為怪奇與人類社會<br>應該保持怎麼樣的關係？',
          ans1: 'A：物競天擇，適者生存。',
          ans1Type: 'fighter',
          ans2: 'B：合為一體，再也不分彼此。',
          ans2Type: 'sacre',
          ans3: 'C：無所謂，反正我都能生存下去。',
          ans3Type: 'wonderer',
          ans4: 'D：合作共榮，攜手創造美好未來。',
          ans4Type: 'naive',
          ans5: 'E：徹底隔絕。（沒有期待，沒有傷害。）',
          ans5Type: 'orphan',
        },
        {
          monster: 'wallet',
          question: '如果你有機會推翻人類社會<br>你會考慮什麼？',
          ans1: 'A：是否符合我心中的正義？',
          ans1Type: 'fighter',
          ans2: 'B：會有怪奇或人受到傷害嗎？',
          ans2Type: 'naive',
          ans3: 'C：我要承擔什麼風險？',
          ans3Type: 'orphan',
          ans4: 'D：我跟人類有什麼恩仇？',
          ans4Type: 'wonderer',
          ans5: 'E：這樣是否能拯救怪奇？',
          ans5Type: 'sacre',
        },
        {
          monster: 'lighter',
          question: '最後，身為怪奇<br>你認為人類是怎麼樣的存在？',
          ans1: 'A：亦敵亦友。',
          ans1Type: 'fighter',
          ans2: 'B：矛盾的混合體。',
          ans2Type: 'wonderer',
          ans3: 'C：朋友。',
          ans3Type: 'naive',
          ans4: 'D：敵人。',
          ans4Type: 'orphan',
          ans5: 'E：悲慘的存在。',
          ans5Type: 'sacre',
        },
      ],
      result: '',
      resultImg: '',
      resultText: {
        'stop': {
          'reason': '基隆市區多為單行道，常有貪圖方便的民眾並排違停，形成車道阻塞、叭聲不斷，纏黏束縛、總是造成周遭怨聲載道。這種「應該不會造成太大困擾吧？」的天真想法，所形成的怪奇，就是名為「違停」的你。',
          'desc': '你時常執著於理想天真幻想世界，喜歡浪漫的偶樣句、甚至喜歡逃避現實。你傾向於不去正視這世界所發生的真實傷害或痛苦，總是認為人們彼此體諒、忍讓，就可以和平相處。但如果知道有多少人恨你的話，可能會讓你大吃一驚唷。'
        },
        'hole': {
          'reason': '基隆從日本時期起就是空襲的主要目標，因而設置的防空洞多不勝數。在戰爭中庇護人們的你，吸收了人類的恐懼，卻在戰後被遺忘，甚至面臨封洞的命運，因此適應黑暗的角落、卻急需安全感，讓你感覺自己被拋棄。',
          'desc': '你時常對於孤獨感到不安，也許你經歷了一段關係的改變，或者是遭到拒絕，而讓你感到挫敗，感覺就好像被全世界抛棄一樣。因此你總是感到不安，覺得他人、世界都是危險的，想尋找一個可以安心的所在。不過也許得自己踏出「洞外」，才有機會找到那個地方唷。'
        },
        'man': {
          'reason': '出現於基隆最潮時期，自覺高人一等、來自全球各地，不凡的生命在被烹煮成咖啡的瞬間就失去了意義，無所事事毫無用途，對存在的困惑生成了怪奇。',
          'desc': '你常因為害怕孤獨而把行程塞得滿滿的，讓自己看起來很忙，無論何時總是自帶著某種歷盡滄桑的漂泊感，還有種淡淡的抑鬱。看似好相處，其實一直讓人很有距離感呢。你總是看著遠方，但會不會你所追尋的答案，就在眼前、腳下某個平凡的角落呢？'
        },
        'cancer': {
          'reason': '你在多雨的基隆如魚得水，觸手深入每個家庭；你比蟑螂更頑強，比野草更會再生，一但被鎖定便會根深柢固死纏爛打⋯⋯沒錯，你就是基隆人聞之色變的怪奇「壁癌」！與基隆嫁妝第一名「除濕機」為死對頭。你在與基隆人的鬥爭中，吸收他們的煩燥感而茁壯，天生就是個鬥士。',
          'desc': '你面對許多來自現實世界的挑戰和問題，等著你去解決，而你必須不斷地鼓舞自己，懂得如何去調節身心、能量、時間和資源，確保你在最佳的狀態。越是艱困的處境，越能激起你的鬥志。但是，總是戰鬥的生活，會不會也有點累呢⋯⋯'
        },
        'bridge': {
          'reason': '為了基隆人通行方便而建，成為城市的一道風景；卻又因都市成長，而成為多餘、甚至礙眼的存在，被厭惡而使人不想靠近，淪為一座一座被拆除的對象。',
          'desc': '你樂於奉獻和付出，甚至是透過犧牲來換取別人的認同。同為不再被城市需要的對象，你並不像「防空洞」一樣感到被遺棄，而是為自己的犧牲奉獻感到滿足。但是太過沈浸在對他人有貢獻的幻想中，可能會忘了為自己好好而活唷。可以再多照顧自己一點嗎？'
        },
      },
      isShowMonster: {
        hole: false,
        stop: false,
        bridge: false,
        cancer: false,
        man: false
      },
      isShowAgain: true
    }
  },
  mounted () {
    
  },
  computed: {

  },
  methods: {
    selectType(type) {
      console.log(type)
      this.qNum++
      if (type == 'naive') {
        this.totalType.naive += 2
        this.totalType.orphan++
        this.totalType.sacre++
      } else if (type == 'orphan') {
        this.totalType.orphan += 2
        this.totalType.naive++
        this.totalType.wonderer++
      } else if (type == 'wonderer') {
        this.totalType.wonderer += 2
        this.totalType.orphan++
        this.totalType.fighter++
      } else if (type == 'fighter') {
        this.totalType.fighter += 2
        this.totalType.sacre++
        this.totalType.wonderer++
      } else {
        this.totalType.sacre += 2
        this.totalType.naive++
        this.totalType.fighter++
      }
      if (this.qNum == 8) {
        this.isShowResult = '解答'
        this.calcMax()
        this.cleanNum()
      }
    },
    calcMax () {
        let arr = Object.values(this.totalType)
        let max = Math.max(...arr)
        if(this.totalType.naive == max) {
          this.result = '違停'
          this.resultImg = 'stop'
        } else if(this.totalType.orphan == max) {
          this.result = '防空洞'
          this.resultImg = 'hole'
        } else if(this.totalType.wonderer == max) {
          this.result = '咖啡渣'
          this.resultImg = 'man'
        } else if(this.totalType.fighter == max) {
          this.result = '壁癌'
          this.resultImg = 'cancer'
        } else {
          this.result = '天橋'
          this.resultImg = 'bridge'
        }
    },
    introMonster (monster) {
      this.isShowAgain = true
      this.isShowResult = '解答'
      if (monster == 'stop') {
        this.result = '違停'
        this.resultImg = 'stop'
      } else if (monster == 'hole') {
        this.result = '防空洞'
        this.resultImg = 'hole'
      } else if (monster == 'man') {
        this.result = '咖啡渣'
        this.resultImg = 'man'
      } else if (monster == 'cancer') {
        this.result = '壁癌'
        this.resultImg = 'cancer'
      } else {
        this.result = '天橋'
        this.resultImg = 'bridge'
      }
    },
    cleanNum () {
      this.qNum = 0
      this.totalType.naive = 0
      this.totalType.orphan = 0
      this.totalType.wonderer = 0
      this.totalType.fighter = 0
      this.totalType.sacre = 0
    }
  },
  watch: {
    
  }
}
</script>

<style lang="scss" scoped>

@keyframes blink {
	0% {
			opacity: 1;
	}
	80% {
			opacity: 1;
	}
	81% {
			opacity: 0;
	}
	100% {
			opacity: 0;
	}
}

.test {
  display: flex;
  justify-content: center;
  background-color: rgb(60, 60, 60);
  min-height: 100vh;

  &-pre {
    width: 100%;
    position: relative;
    background-image: url('../assets/img/test/bg/test-01.jpeg');
    background-repeat: no-repeat;
    background-size: contain;
    background-position-x: center;
    background-position-y: center;
    background-attachment: fixed;
    padding: 0px 30px 14px;

    &-img-box {
      text-align: right;
    }
    
    &-img {
      position: absolute;
      top: 20px;
      right: calc(40% - 100px);
      width: 150px;
    }

    &-text-box {
      max-width: 270px;
      margin: 210px auto 0px;
    }

    &-text {
      font-size: 18px;
      line-height: 1.5;
    }

    &-start-box {
      display: flex;
      justify-content: flex-end;
    }

    &-start {
      width: 120px;
      margin: 30px auto 0px;
      padding: 10px 0px;
      border-radius: 20px;
      text-align: center;
      background-color: #96ff3c;
      color: black;
      cursor: pointer;
    }
  }

  &-qa {
    width: 100%;
    position: relative;
    background-image: url('../assets/img/test/bg/bg2.jpg');
    background-repeat: no-repeat;
    background-size: contain;
    background-position-x: center;
    background-position-y: center;
    background-attachment: fixed;
    padding: 14px 20px;

    &-img-box {
      display: flex;
      justify-content: space-between;
      align-items: baseline;
      margin-top: 20px;
    }

    &-num {
      font-size: 60px;
      color: rgb(65, 65, 65);
    }

    &-img {
      height: 110px;
    }

    &-question {
      font-size: 20px;
      margin-bottom: 16px;
      line-height: 1.5;
    }

    &-answer {
      margin-top: 12px;
      padding: 10px 10px;
      font-size: 18px;
      color: black;
      background-color: rgb(204, 200, 199);
      cursor: pointer;
    }
  }

  &-result {
    width: 100%;
    position: relative;
    min-height: calc(100vh - 28px);
    text-align: center;
    background-image: url('../assets/img/test/bg/bg3.jpg');
    background-repeat: no-repeat;
    background-size: contain;
    background-position-x: center;
    background-position-y: center;
    background-attachment: fixed;

    &-img {
      width: 250px;
      margin-top: 60px;
    }

    &-img-tall {
      width: 150px;
    }

    &-text {
      font-size: 20px;
    }

    &-text-btn {
      width: 140px;
      margin: 20px auto 0px;
      padding: 6px 0px 6px 16px;
      letter-spacing: 16px;
      text-align: center;
      font-size: 24px;
      background-color: rgba(20, 75, 7, 0.6);
      border-radius: 30px;
    }

    &-next {
      margin-top: 40px;
      width: 30px;
      cursor: pointer;
    }
  }

  &-desc {
    width: 100%;
    position: relative;
    min-height: calc(100vh - 28px);
    display: flex;
    flex-direction: column;
    align-items: center;
    background-image: url('../assets/img/test/bg/test-01.jpeg');
    background-repeat: no-repeat;
    background-size: contain;
    background-position-x: center;
    background-position-y: center;
    background-attachment: fixed;
    padding: 10px 0px;

    &-img {
      // position: absolute;
      // right: 36px;
      // top: 90px;
      height: 180px;
    }

    &-img-small {
      height: 150px;
    }

    &-img-smaller {
      height: 130px;
    }

    &-name {
      width: 120px;
      margin: 20px 0px 8px;
      padding: 6px 0px 6px 6px;
      letter-spacing: 6px;
      text-align: center;
      font-size: 24px;
      font-weight: bold;
      color: black;
      background-color:#96ff3c;
      border-radius: 30px;
    }

    &-sub {
      width: calc(100% - 60px);
      margin: 24px 30px 0px;
      color: #96ff3c;
      font-size: 20px;
    }

    &-text {
      width: calc(100% - 60px);
      margin: 12px 30px 0px;
      line-height: 1.3;
      text-align: justify;
      font-size: 18px;
    }

    &-desc {
      position: relative;
      bottom: 0px;
      margin-top: 40px;
      padding: 15px 20px 30px;
      line-height: 1.3;
      color: black;
      background-color: rgb(139, 138, 144);
      text-align: justify;
      font-size: 18px;
    }

    &-next {
      position: absolute;
      bottom: 15px;
      right: 20px;
      width: 30px;
      cursor: pointer;
    }
  }

  &-re {
    position: relative;
    max-width: 380px;
    width: 240px;
    min-height: calc(100vh - 28px);
    background-image: url('../assets/img/test/bg/bg4.jpg');
    background-repeat: no-repeat;
    background-size: contain;
    background-position-x: center;
    background-position-y: center;
    background-attachment: fixed;
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 14px 36px;

    &-img {
      position: absolute;

      &:nth-child(1) {
        width: 160px;
        top: 10px;
        left: 20px;
	      animation-delay: 1s;
	      animation-duration: 0.6s;
        animation-name: blink;
        animation-iteration-count: infinite;
        animation-direction: alternate;
        animation-timing-function: ease-in-out;
      }

      &:nth-child(2) {
        width: 80px;
        top: 30px;
        right: 20px;
	      animation-delay: 2s;
	      animation-duration: 0.6s;
        animation-name: blink;
        animation-iteration-count: infinite;
        animation-direction: alternate;
        animation-timing-function: ease-in-out;
      }

      &:nth-child(3) {
        width: 220px;
        top: 140px;
        left: 70px;
	      animation-delay: 3s;
        animation-duration: 0.6s;
        animation-name: blink;
        animation-iteration-count: infinite;
        animation-direction: alternate;
        animation-timing-function: ease-in-out;
      }

      &:nth-child(4) {
        width: 120px;
        top: 260px;
        left: 10px;
	      animation-delay: 4s;
        animation-duration: 0.6s;
        animation-name: blink;
        animation-iteration-count: infinite;
        animation-direction: alternate;
        animation-timing-function: ease-in-out;
        
      }

      &:nth-child(5) {
        width: 200px;
        top: 280px;
        right: 10px;
	      animation-delay: 5s;
        animation-duration: 0.6s;
        animation-name: blink;
        animation-iteration-count: infinite;
        animation-direction: alternate;
        animation-timing-function: ease-in-out;
        
      }

    }

    &-btn-box {
      width: 100%;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      text-align: center;
      z-index: 1;
    }

    &-return {
      width: 50px;
      cursor: pointer;
    }

    &-text {
      margin: 10px 0px 30px;
      letter-spacing: 10px;
      color: #96ff3c;
      cursor: pointer;
    }

    &-btn {
      width: 240px;
      margin: 20px auto 0px;
      padding: 8px 0px 8px 2px;
      letter-spacing: 2px;
      text-align: center;
      font-size: 16px;
      background-color: rgba(20, 75, 7, 0.6);
      border-radius: 30px;
      cursor: pointer;
    }
  }

}

@media( max-width: 500px ){

}

</style>
