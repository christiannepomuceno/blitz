<template>
  <ul :class="['navigation-menu', toggle ? 'open' : '']">
    <li v-for="i in items" :key="i.text">
      <a :href="i.link">{{ i.text }}</a>
    </li>
  </ul>
</template>

<script>
export default {
  name: 'navbar',
  props: {
    toggle: {
      type: Boolean,
      default: false
    },
    items: {
      type: Array,
    }
  }
}
</script>

<style lang="scss" scoped>
.navigation-menu {
  position: absolute;
  margin-top: 80px;
  padding-left: 0;
  width: 100%;
  height: 300px;
  opacity: 0;
  transform: translateY(300px);
  transition: transform 1s, opacity 1s;

  &.open {
    opacity: 1;
    transform: translateY(0)
  }

  li {
    float: left;
    width: calc(100% / 3);
    height: calc(300px / 3);
    text-align: center;
    text-transform: uppercase;
    list-style: none;

    a {
      color: #cecece;
      text-decoration: none;
      font-size: 0.85em;
      font-weight: bold;
      position: relative;
      letter-spacing: 1px;
      text-transform: uppercase;
    }
  }
}
</style>