<template>
  <div class="test">
    <div v-if="isShowResult == '前言'" class="test-result">
      <div class="test-pre">
        探員⋯⋯不，應該稱呼你為「怪奇」了。經過一番歷險的你，終於找回自己的真實身份。但是不同的怪奇，是由不同的、糾結的「議題」所形成的。你可曾想過，自己究竟誕生自什麼議題呢？<br><br>
        回答下面這些問題，說說你在這個人類主宰的世界，會怎麼生存下去。那麼我將能告訴你，你是什麼怪奇？
      </div>
      <div class="test-start" @click="isShowResult = '題目'">開始測驗！</div>
    </div>
    <div v-else-if="isShowResult == '解答'" class="test-result">
      <div class="test-result-text">你是 {{ result }}！</div>
    </div>
    <div v-else class="test-qa">
      <div >
        <div class="test-question">{{ qa[qNum].question }}</div>
        <div @click="selectType(qa[qNum].ans1Type)" class="test-answer">{{ qa[qNum].ans1 }}</div>
        <div @click="selectType(qa[qNum].ans2Type)" class="test-answer">{{ qa[qNum].ans2 }}</div>
        <div @click="selectType(qa[qNum].ans3Type)" class="test-answer">{{ qa[qNum].ans3 }}</div>
        <div @click="selectType(qa[qNum].ans4Type)" class="test-answer">{{ qa[qNum].ans4 }}</div>
        <div @click="selectType(qa[qNum].ans5Type)" class="test-answer">{{ qa[qNum].ans5 }}</div>
      </div>
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
          question: '1.在面對人類不友善的眼光時，你的反應是？',
          ans1: 'A：人類應該是對我有什麼誤會吧？',
          ans1Type: 'naive',
          ans2: 'B：人類真是好可怕啊！',
          ans2Type: 'orphan',
          ans3: 'C：不友善眼光又怎麼樣？',
          ans3Type: 'wonderer',
          ans4: 'D：竟敢用這種態度對待我們怪奇！',
          ans4Type: 'fighter',
          ans5: 'E：該為我們怪奇社群做些什麼。',
          ans5Type: 'sacre',
        },
        {
          question: '2.你擁有怪奇獨有的特殊、強大能力，你會？',
          ans1: 'A：唯我獨尊。',
          ans1Type: 'fighter',
          ans2: 'B：保護弱小怪奇。',
          ans2Type: 'sacre',
          ans3: 'C：這些特殊能力好有趣啊！',
          ans3Type: 'naive',
          ans4: 'D：擁有強大能力，才能保護自己。',
          ans4Type: 'orphan',
          ans5: 'E：我可以靠這個能力做些特別的事！',
          ans5Type: 'wonderer',
        },
        {
          question: '3.對於身旁有著各式特異的怪奇，你怎麼看待？',
          ans1: 'A：有好多朋友真好。',
          ans1Type: 'naive',
          ans2: 'B：其他怪奇會不會想對我不利？',
          ans2Type: 'orphan',
          ans3: 'C：我要守護這份友誼。',
          ans3Type: 'sacre',
          ans4: 'D：大家能力都很不錯呢！',
          ans4Type: 'fighter',
          ans5: 'E：大家都很有自己的特色嘛！',
          ans5Type: 'wonderer',
        },
        {
          question: '4.在這個人類與怪奇共存的社會中，你會致力於？',
          ans1: 'A：獨善其身。',
          ans1Type: 'orphan',
          ans2: 'B：守護怪奇社會和平。',
          ans2Type: 'sacre',
          ans3: 'C：融入社會。',
          ans3Type: 'naive',
          ans4: 'D：才不管社會不社會，我要去尋找刺激。',
          ans4Type: 'wonderer',
          ans5: 'E：我要來為社會做點什麼。',
          ans5Type: 'fighter',
        },
        {
          question: '5.當你在成長過程中，面對人類持續不斷的追殺時，你的反應是？',
          ans1: 'A：直接面對。',
          ans1Type: 'fighter',
          ans2: 'B：為什麼要這樣對我。',
          ans2Type: 'naive',
          ans3: 'C：我願意犧牲來保護其他怪奇。',
          ans3Type: 'sacre',
          ans4: 'D：該是我表現的時候。',
          ans4Type: 'wonderer',
          ans5: 'E：我好害怕…',
          ans5Type: 'orphan',
        },
        {
          question: '6.看到比你弱小的怪奇，你是怎麼看待？',
          ans1: 'A：應該要努力變更強才對。',
          ans1Type: 'fighter',
          ans2: 'B：讓我保護你們吧！',
          ans2Type: 'sacre',
          ans3: 'C：我還是顧好自己就好。',
          ans3Type: 'wonderer',
          ans4: 'D：無論強弱，我們都可以是朋友。',
          ans4Type: 'naive',
          ans5: 'E：我們都需要被保護啊。',
          ans5Type: 'orphan',
        },
        {
          question: '7.你受到其他怪奇邀請，意圖推翻人類世界，你會？',
          ans1: 'A：符合正義的事，我都願意做。',
          ans1Type: 'fighter',
          ans2: 'B：真的有必要這樣嗎？',
          ans2Type: 'naive',
          ans3: 'C：我覺得怪奇跟人類都很可怕。',
          ans3Type: 'orphan',
          ans4: 'D：我過好自己的生活就好了。',
          ans4Type: 'wonderer',
          ans5: 'E：當然要加入，我要盡力保護怪奇們。',
          ans5Type: 'sacre',
        },
        {
          question: '8.身為怪奇，你認為人類是？',
          ans1: 'A：可能是敵人。',
          ans1Type: 'fighter',
          ans2: 'B：另一種生物。',
          ans2Type: 'wonderer',
          ans3: 'C：能和平共處的對象。',
          ans3Type: 'naive',
          ans4: 'D：危險生物。',
          ans4Type: 'orphan',
          ans5: 'E：若人類會傷害怪奇，他們就不是我的朋友。',
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

  &-pre {
    margin-top: 20px;
    font-size: 26px;
    line-height: 1.3;
  }

  &-start {
    margin-top: 30px;
    text-align: center;
    padding: 20px 0px;
    background-color: bisque;
    cursor: pointer;
  }

  &-result {
    max-width: 420px;
    padding: 14px;
  }

  &-result-text {
    font-size: 24px;
  }

  &-qa {
    max-width: 420px;
    padding: 14px;
  }

  &-question {
    font-size: 24px;
    margin-bottom: 20px;
    line-height: 1.5;
  }

  &-answer {
    margin-top: 26px;
    background-color: bisque;
    padding: 10px 10px;
  }

}

@media( max-width: 500px ){

}

</style>
