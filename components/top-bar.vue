<template>
  <div class="top">
    <div v-if="!isPopup" class="top-bar">
      <div class="top-bar-social">
        <a href="https://www.facebook.com/ChiKuWainKeelung" target="_blank">
          <img class="top-bar-social-icon" src="@/assets/img/index/fb.png" alt="menu">
        </a>
        <!-- <img class="top-bar-social-icon" src="@/assets/img/index/ig.png" alt="menu"> -->
      </div>
      <img @click="isPopup = true" class="top-bar-menu" src="@/assets/img/index/menu.png" alt="menu">
    </div>
    <div v-else class="top-popup">
      <div class="top-popup-close-box">
        <img @click="isPopup = false" class="top-popup-close" src="@/assets/img/index/close.png" alt="menu">
      </div>
      <div @click="scrollToRef('top')" class="top-popup-text">怪奇逃走中</div>
      <div @click="scrollToRef('about')" class="top-popup-text">關於怪奇</div>
      <div @click="scrollToRef('run')" class="top-popup-text">通緝中</div>
      <div @click="scrollToRef('time')" class="top-popup-text">平行時空</div>
      <div @click="scrollToRef('musium')" class="top-popup-text">怪奇博物館</div>
      <div @click="scrollToRef('qa')" class="top-popup-text">Q&amp;A</div>
    </div>
  </div>
</template>

<script>
export default {
  components: {

  },
  props: {
    
  },
  data () {
    return {
      isPopup: false
    }
  },
  computed: {

  },
  methods: {
    scrollToRef(id) {
      this.isPopup = false
      this.$emit('scrollToRefs', id)
    }
  },
  watch: {
    
  }
}
</script>

<style lang="scss">

.top {
  display: none;
}

@media( max-width: 1023px ){

.top {
  display: block;
  position: fixed;
  top: 0px;
  left: 0px;
  width: 100%;
  z-index: 3;

  &-bar {
    width: calc(100% -40px);
    height: 50px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 0px 20px;
    background-color: rgb(0, 36, 93);

    &-social {
      margin: 10px 0px 0px 20px;

      &-icon {
        height: 20px;
      }
    }

    &-menu {
      width: 30px;
    }
  }

  &-popup {
    width: calc(100% -40px);
    height: 100vh;
    padding: 0px 20px;
    background-color: rgb(25, 14, 64);

    &-close-box {
      text-align: right;
      padding: 24px 0px 10px;
    }

    &-close {
      width: 30px;
    }

    &-text {
      margin-top: 32px;
      text-align: center;
      color: white;
      font-size: 22px;
      font-weight: bold;
    }
  }
}

}

</style>