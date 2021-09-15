<template>
  <div class="test">

    <!-- 前言 -->
    <div v-if="isShowResult == '前言'" class="test-pre">

      <img class="test-pre-img" src="@/assets/img/test/monster/fish.png" alt="">

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
          <img class="test-qa-img" :src="require(`@/assets/img/test/monster/${qa[qNum].monster}.png`)" alt="">
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
      <div class="test-result-text">你是 {{ result }}！</div>
    </div>

    
  </div>
</template>

<script>

export default {
  head: {
    title: '小怪奇測驗',
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
      result: '',
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
      ]
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
      }
    },
    calcMax () {
        let arr = Object.values(this.totalType)
        let max = Math.max(...arr)
        if(this.totalType.naive == max) {
          this.result = '天真者'
        } else if(this.totalType.orphan == max) {
          this.result = '孤兒'
        } else if(this.totalType.wonderer == max) {
          this.result = '流浪者'
        } else if(this.totalType.fighter == max) {
          this.result = '鬥士'
        } else {
          this.result = '殉道者'
        }
    }
  },
  watch: {
    
  }
}
</script>

<style lang="scss" scoped>

.test {
  display: flex;
  justify-content: center;
  background-color: rgb(60, 60, 60);

  &-pre {
    position: relative;
    max-width: 440px;
    min-height: calc(100vh - 28px);
    background: url('../assets/img/test/bg/bg1.jpg');
    background-repeat: no-repeat;
    background-size: contain;
    background-position-x: center;
    background-position-y: center;
    background-attachment: fixed;
    padding: 14px 30px;

    &-img-box {
      text-align: right;
    }
    
    &-img {
      position: absolute;
      top: 20px;
      right: 80px;
      width: 130px;
    }

    &-text-box {
      margin-top: 170px;
    }

    &-text { 
      font-size: 14px;
      line-height: 1.5;
    }

    &-start-box {
      display: flex;
      justify-content: flex-end;
    }

    &-start {
      width: 120px;
      margin-top: 30px;
      padding: 10px 0px;
      border-radius: 20px;
      text-align: center;
      background-color: #96ff3c;
      color: black;
      cursor: pointer;
    }
  }

  &-qa {
    position: relative;
    max-width: 300px;
    min-height: calc(100vh - 28px);
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
      font-size: 18px;
      margin-bottom: 16px;
      line-height: 1.5;
    }

    &-answer {
      width: 260px;
      margin-top: 12px;
      padding: 10px 10px;
      font-size: 14px;
      color: black;
      background-color: rgb(204, 200, 199);
    }
  }

  &-result {
    position: relative;
    max-width: 300px;
    min-height: calc(100vh - 28px);
    background-image: url('../assets/img/test/bg/bg3.jpg');
    background-repeat: no-repeat;
    background-size: contain;
    background-position-x: center;
    background-position-y: center;
    background-attachment: fixed;
    padding: 14px 60px;

    &-text {
      font-size: 24px;
    }
  }

  

}

@media( max-width: 500px ){

}

</style>
