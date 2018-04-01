<template>
    <transition name="fade" @after-enter="transitionComplete">
      <div class="app-toast" v-if="show">
        {{ text }}
      </div>
    </transition>
  
</template>

<script>
export default {
  name:'toast',
  props:{
    text:String,
    value:Boolean
  },
  data () {
    return {
      show:false
    }
  },
  watch:{
    value (val) {
      this.show = val
    }
  },
  methods: {
    transitionComplete: function (el) {
      this.show = false
    }
  }
}
</script>

<style scoped lang="scss">
  *{
    margin: 0;
    padding: 0;
  }
  .app-toast{
    position:fixed;
    padding: 15px 8px;
    border-radius: 4px;
    min-width: 100px;
    color: rgb(255,255, 255);
    text-align: center;
    font-size: 13px;
    background-color: rgba(0, 0, 0, 0.8);
    left: 50%;
    top: 50%;
    z-index: 9999;
    transform: translate(-50%,-50%);
  }
  .fade-enter-active, .fade-leave-active {
    transition: opacity .3s;
  }
  .fade-enter, .fade-leave-to {
    opacity: 0;
  }
</style>

