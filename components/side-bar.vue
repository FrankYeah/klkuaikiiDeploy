<template>
  <div class="side">
    <div @click="scrollToRef('top')" class="side-circle">
      <div v-show="circle.one" class="side-circle-text">怪奇逃走中</div>
      <div @mouseover="circle.one = true" @mouseleave="circle.one = false"
        :class="['side-circle-circle', {'side-circle-circle-full': circle.one}]"
      ></div>
    </div>
    <div @click="scrollToRef('about')" class="side-circle">
      <div v-show="circle.two" class="side-circle-text">關於怪奇</div>
      <div @mouseover="circle.two = true" @mouseleave="circle.two = false"
        :class="['side-circle-circle', {'side-circle-circle-full': circle.two}]"
      ></div>
    </div>
    <div @click="scrollToRef('run')" class="side-circle">
      <div v-show="circle.three" class="side-circle-text">通緝中</div>
      <div @mouseover="circle.three = true" @mouseleave="circle.three = false"
        :class="['side-circle-circle', {'side-circle-circle-full': circle.three}]"
      ></div>
    </div>
    <div @click="scrollToRef('time')" class="side-circle">
      <div v-show="circle.four" class="side-circle-text">平行時空</div>
      <div @mouseover="circle.four = true" @mouseleave="circle.four = false"
        :class="['side-circle-circle', {'side-circle-circle-full': circle.four}]"
      ></div>
    </div>
    <div @click="scrollToRef('musium')" class="side-circle">
      <div v-show="circle.five" class="side-circle-text">怪奇博物館</div>
      <div @mouseover="circle.five = true" @mouseleave="circle.five = false"
        :class="['side-circle-circle', {'side-circle-circle-full': circle.five}]"
      ></div>
    </div>
    <div @click="scrollToRef('qa')" class="side-circle">
      <div v-show="circle.six" class="side-circle-text">Q&amp;A</div>
      <div @mouseover="circle.six = true" @mouseleave="circle.six = false"
        :class="['side-circle-circle', {'side-circle-circle-full': circle.six}]"
      ></div>
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
      circle: {
        one: false,
        two: false,
        three: false,
        four: false,
        five: false,
        six: false
      }
    }
  },
  computed: {

  },
  methods: {
    scrollToRef(id) {
      this.$emit('scrollToRefs', id)
    }
  },
  watch: {
    
  }
}
</script>

<style lang="scss">

.side {
  position: fixed;
  right: 40px;
  top: 30vh;
  
  &-circle {
    height: 20px;
    margin-bottom: 16px;
    display: flex;
    justify-content: flex-end;
    align-items: center;
    cursor: pointer;

    &-text {
      margin-right: 10px;
      color: white;
      text-align: right;
    }

    &-circle {
      width: 8px;
      height: 8px;
      border-radius: 100%;
      border: 2px solid white;
    }

    &-circle-full {
      background-color: white;
    }
  }
}

@media( max-width: 1023px ){

.side {
  display: none;
}

}

</style>