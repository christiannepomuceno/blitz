<template>
  <div :class="['content-wrapper', show ? 'move' : '']" @click="clickHandler">
    <div class="inner">
      <mainHeader></mainHeader>
      <getQuote></getQuote>
      <brand></brand>
      <platform></platform>
      <business></business>
      <great></great>
      <mainFooter></mainFooter>
    </div>
  </div>
</template>

<script>
import mainHeader from './content/Header.vue'
import getQuote from './content/GetQuote.vue'
import brand from './content/Brand.vue'
import platform from './content/Platform.vue'
import business from './content/Business.vue'
import great from './content/Great.vue'
import mainFooter from './content/Footer.vue'

export default {
  name: 'wrapper',
  components: {
    mainHeader,
    getQuote,
    brand,
    platform,
    business,
    great,
    mainFooter
  },
  props: {
    show: {
      type: Boolean,
      default: false
    }
  },
  data () {
    return {

    }
  },
  methods: {
    clickHandler(event) {
      this.$emit("click", event);
    },
  }
}
</script>

<style lang="scss" scoped>
$bg-color: #2a2b30;

.content-wrapper {
  position: relative;
  width: 100%;
  background-color: $bg-color;
  height: 100vh;
  transform: scale(1);
  perspective: 1;
  transition: .45s cubic-bezier(0.6, 0, 0.4, 1) all;
  box-shadow: 0 -1px 10px rgba(0, 0, 0, 0.1);
 
  &:after,
  &:before {
    content: '';
    position: absolute;
    top: 0;
    left: 50%;
    z-index: -1;
    width: 95%;
    height: 50%;
    transform: translateX(-50%) translateY(50px);
    background-color: $bg-color;
    transition: .45s cubic-bezier(0.6, 0, 0.4, 1) all;
    box-shadow: 0 -1px 10px rgba(0, 0, 0, 0.1);
  }

  &:after {
    width: 90%;
    z-index: -2;
  }
 
  &.move {
    position: absolute;
    transform: scale(.8) translateY(50%);

    &:before {
      transform: translateX(-50%) translateY(-25px)
    }

    &:after {
      transform: translateX(-50%) translateY(-50px)
    }
  }
 
  .inner {
    display: block;
    position: relative;
    width: 100%;
    height: 100%;
    overflow: auto;
    overflow-x: hidden;
    background-color: $bg-color;
    box-shadow: 0 -1px 10px rgba(0, 0, 0, 0.1);
  }
}
</style>