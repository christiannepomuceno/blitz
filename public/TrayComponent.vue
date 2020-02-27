<template>
  <div class="tray">
    <StatisticsComponent mini :data="statsData" />
  </div>
</template>

<script>
import StatisticsComponent from '@/components/video/tray/StatisticsComponent'
export default {
  components: {
    StatisticsComponent
  },
  data () {
    return {
      statsData: [
        {
          className: 'blue',
          code: 'D',
          userCount: 5,
          totalBet: 25000
        },
        {
          className: 'green',
          code: 'T',
          userCount: 3,
          totalBet: 10000
        },
        {
          className: 'red',
          code: 'T',
          userCount: 1,
          totalBet: 3000
        },
        {
          className: 'star',
          code: '★',
          userCount: 1,
          totalBet: 1000
        }
      ]
    }
  },
}
</script>

<style lang="scss" scoped>
  $class: '.tray';
  $tray-height: 256px;

  #{$class} {
    position: absolute;
    z-index: 1;
    top: -40px;
    width: 100%;
    @include rem(height, $tray-height);

    > div {
      height: 100%;
      background-color: rgba($base-color,.5);
    }
  }
</style>