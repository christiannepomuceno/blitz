<template>
  <div id="app">
    <sticky :class="['toolbar']" :top="900">
      <div class="logo"></div>
      <button :class="['menu-click', openMenu ? 'toggle' : '']" @click="openMenu = !openMenu">
        <span></span>
      </button>
    </sticky>
    <navigation :toggle="openMenu" :items="list"></navigation>
    <wrapper :show="openMenu" @click="openMenu = false"></wrapper>
  </div>
</template>

<script>
import sticky from './components/StickyTop.vue'
import navigation from './components/Navigation.vue'
import wrapper from './components/Wrapper.vue'

export default {
  name: 'app',
  components: {
    sticky,
    navigation,
    wrapper
  },
  data () {
    return {
      openMenu: false,
      list: [
        {
          text: 'Home',
          link: ''
        },
        {
          text: 'Documentation',
          link: ''
        },
        {
          text: 'Manuals',
          link: ''
        },
        {
          text: 'Software',
          link: ''
        },
        {
          text: 'Customization & Settings',
          link: ''
        },
        {
          text: 'Training',
          link: ''
        },
        {
          text: 'Where to buy',
          link: ''
        },
        {
          text: 'Blog & News',
          link: ''
        },
        {
          text: 'Contact',
          link: ''
        },
      ]
    }
  },
}
</script>

<style lang="scss">
html,
body {
  background-color: #1d1e21;
  color: #3A3C3B;
  margin: 0;
  padding: 0;
  overflow: hidden;
  font-size: 16px;
}

#app {
  font-family: 'Montserrat';
  -webkit-font-smoothing: antialiased;
  overflow: hidden;
}

.primary {
  display: inline-flex;
  justify-content: center;
  align-items: center;
  width: 230px;
  height: 70px;
  border: 0;
  text-transform: uppercase;
  letter-spacing: 3px;
  font-size: 1.25em;
  color: #fff;
  background: linear-gradient(145deg, #ff5891 0%, 50%,#863ea3 100%);
  cursor: pointer;
}

.logo {
  width: 100px;
  height: 50px;
  background-image: url('~@/assets/hustle.png');
  background-size: contain;
  background-position: left center;
  background-repeat: no-repeat;
}
</style>
