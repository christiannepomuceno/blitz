<template>
  <div class="sticky">
    <slot></slot>
  </div>
</template>

<script>
export default {
  name: 'sticky',
  props: {
    top: {
      type: Number,
      default: 0
    },
  },
  data () {
    return {
      scrolled: null
    }
  },
  methods: {
    handleScroll () {
      const el = document.querySelector('.inner')
      const sticky = document.querySelector('.sticky')
      const fadeText = document.querySelector('.fadeText')
      const great = document.querySelector('.great')
      const business = document.querySelector('.business')
      const parallax = document.querySelectorAll('.parallax')
      const list = document.querySelector('#great')

      this.scrolled = el.scrollTop

      if(this.scrolled > this.$props.top) {
        sticky.classList.add('scrolling')
      } else {
        sticky.classList.remove('scrolling')
      }

      fadeText.setAttribute('style', 
        `transform: translateY(${ -100 * (this.scrolled / this.$props.top) + 'px'}); opacity: ${ 1 - (this.scrolled / this.$props.top)}`,
      )
      
      if(this.scrolled > business.offsetTop) {
        great.setAttribute('style', 
          `opacity: ${ 4 * (this.scrolled - business.offsetTop ) / this.scrolled }`,
        )
        list.setAttribute('style', 
          `opacity: ${ 5 * (this.scrolled - business.offsetTop ) / this.scrolled }`,
        )
      } else {
        great.setAttribute('style', 
          `opacity: 0`,
        )
        list.setAttribute('style', 
          `opacity: 0`,
        )
      }

      if(this.scrolled > business.offsetTop + this.$props.top ) {
        list.classList.add('show')
      } else {
        list.classList.remove('show')
      }

      for (var i = 0; i < parallax.length; i++) {
        parallax[i].setAttribute('style', 
          `transform: translateY(${ this.scrolled / this.$props.top * 100 + 'px'})`,
        )
      }
    }
  },
  watch: {
    top: function(n) {
      if (n) {
        this.handleScroll()
      }
    }
  },
  mounted () {
    this.handleScroll()
    const el = document.querySelector('.inner')
    el.addEventListener('scroll', this.handleScroll)
  },
  destroyed () {
    this.handleScroll()
    const el = document.querySelector('.inner')
    el.removeEventListener('scroll', this.handleScroll)
  }
}
</script>

<style lang="scss">
.toolbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 999;
  height: 50px;
  padding: 16px;

  img {
    height: 100%;
  }

  &.scrolling {

    .menu-click {
      &:before,
      &:after,
      span {
        background-color: #000;
      }
    }

    .logo {
      background-image: url('~@/assets/logo-black.png')
    }
  }
}

.menu-click {
  position: relative;
  float: right;
  width: 30px;
  height: 24px;
  margin: 20px;
  background-color: transparent;
  border: 0;
  cursor: pointer;
 
  &:before,
  &:after,
  span {
    background-color: #fff;
  }
 
  &:before,
  &:after {
    content: '';
    position: absolute;
    top: 50%;
    left: 0;
    width: 100%;
    height: 2px;
    pointer-events: none;
    transition: transform 0.25s;
    transform-origin: 50% 50%;
  }
 
  &:before {
    transform: translate3d(0, -10px, 0) scale3d(0.8, 1, 1);
  }
 
  &:after {
    transform: translate3d(0, 10px, 0) scale3d(0.8, 1, 1);
  }
 
  span {
    position: absolute;
    left: 0;
    overflow: hidden;
    width: 100%;
    height: 2px;
    text-indent: 200%;
    transition: opacity 0.25s;
  }
 
  &.toggle {

    &:before {
      transform: rotate3d(0, 0, 1, 45deg);
      background-color: #fff !important
    }

    &:after {
      transform: rotate3d(0, 0, 1, -45deg);
      background-color: #fff !important
    }

    span {
      opacity: 0;
    }
  }
}
</style>