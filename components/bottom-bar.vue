<template>
  <div class="bottom">
    <div class="bottom-text">Copyright 2021 雞籠怪奇博物館</div>
    <div class="bottom-text">All Rights Reserved | Powered by 雞籠怪奇博物館</div>
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

    }
  },
  computed: {

  },
  methods: {

  },
  watch: {
    
  }
}
</script>

<style lang="scss">

.bottom {
  padding: 30px 0px 60px;
  font-size: 20px;
  text-align: center;
  background-color: rgb(17, 17, 82);

  &-text {
    color: #96ff3c;
    margin-top: 8px;
  }
}

@media( max-width: 500px ){

.bottom {
  padding: 15px 14px 30px;
  font-size: 14px;

  &-text {
    line-height: 1.4;
  }
}

}

</style>