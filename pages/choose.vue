<template>
  <div class="choose"
    v-lazy:background-image="require('@/assets/img/index/bg-blue.png')"
  >
    <div class="choose-box">
      <img class="choose-head-img" v-lazy="require('@/assets/img/index/text-main.png')" alt="main">
      <div class="choose-head">遊戲之後，也許你會有興趣......</div>
      <div class="choose-hand" v-lazy:background-image="require('@/assets/img/index/monster-hand.png')"></div>
      <div class="choose-select">
        <router-link :to="'/literacy'">
          <div class="choose-btn choose-btn-first">關於素養</div>
        </router-link>
        <a href="https://forms.gle/GLhuHiQY1kby9x7E8" target="_blank">
          <div class="choose-btn choose-btn-center">回饋問卷</div>
        </a>
        <a href="https://www.surveycake.com/admin/tw/survey/em0N4/report?v=0e8e0765b9b0ed11da8abdd96b8d3bcd&layout=P" target="_blank">
          <div class="choose-btn choose-btn-last">最終抉擇統計數據</div>
        </a>
      </div>
      <div class="choose-copyright">
        Copyright 2021 雞籠怪奇博物館<br>
        All Rights Reserved｜Powered by 雞籠怪奇博物館
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

  .choose {
    min-width: 100vw;
    min-height: 100vh;
    height: 100%;
    background-repeat: no-repeat;
    background-size: cover;
    background-position-x: center;
    background-position-y: center;

    &-box {
      max-width: 800px;
      width: 100%;
      margin: auto;
      padding: 30px 0px 30px;
    }

    &-head-img {
      width: 400px;
    }

    &-head {
      font-size: 20px;
      margin-top: 30px;
    }

    &-hand {
      position: absolute;
      right: 60px;
      top: 50px;
      width: 600px;
      height: 300px;
      background-repeat: no-repeat;
      background-size: cover;
      background-position-x: center;
      background-position-y: center;
      transform: rotate(20deg) scaleX(-1);
    }

    &-select {
      display: flex;
      justify-content: center;
      align-items: center;
      margin: 50px 0px 40px;
    }

    &-btn {
      width: 90px;
      height: 90px;
      margin: 0px 10px;
      padding: 14px;
      line-height: 30px;
      display: flex;
      align-items: center;
      font-size: 22px;
      text-align: center;
      border-radius: 100%;
      background-color: black;
      cursor: pointer;

      &:hover {
        background-color: rgb(255, 220, 0);
        color: black;
      }
    }

    &-btn-last {
      position: relative;
      
      &::after {
        content: "統計持續更新中";
        position: absolute;
        left: 1px;
        bottom: -33px;
        width: 120px;
        font-size: 14px;
      }

      &:hover {
        color: white;
      }
    }

    &-copyright {
      padding: 30px 0px 10px;
      line-height: 1.4;
      text-align: center;
    }
  }

  @media( max-width: 1023px ){

  .choose {
    

    &-box {
      display: flex;
      flex-direction: column;
      align-items: center;
    }

    &-head-img {
      width: 280px;
    }

    &-head {
      font-size: 18px;
      margin-top: 20px;
    }

    &-hand {
      width: 180px;
      height: 90px;
      top: 222px;
      right: 11px;
      transform: rotate(20deg) scaleX(-1);
    }

    &-select {
      flex-direction: column;
      margin: 50px 0px 40px;
    }

    &-btn {
      
    }

    &-btn-first {
    transform: translateX(-70px);
    }

    &-btn-center {
      transform: translateX(70px);
    }

    &-btn-last {
      transform: translateX(-70px);
      
      &::after {
        
      }
    }

    &-copyright {
      font-size: 14px;
    }
  }

}

</style>
