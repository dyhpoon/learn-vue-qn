<template>
  <div class="header">
    <div class="header-left">
      <div class="iconfont back-icon">&#xe624;</div>
    </div>
    <div class="header-input">
      <span class="iconfont">&#xe632;</span>
      Cities/Places
      </div>
    <router-link to="/city">
      <div class="header-right">
        {{currentCity}}
        <span class="iconfont arrow-icon">&#xe64a;</span>
      </div>
    </router-link>
  </div>
</template>

<script>
import { mapState } from 'vuex'
export default {
  name: 'HomeHeader',
  computed: {
    ...mapState(['city']),
    currentCity () {
      const firstLetter = this.city.charAt(0).toUpperCase()
      const restLetters = this.city.slice(1)
      return firstLetter + restLetters
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~@styles/variables.styl';
  .header
    display: flex
    line-height: $headerHeight // html font-size is 50px, height is 86px@2x (43px@1x)
    background: $bgColor
    color: #fff
    .header-left
      width: .64rem
      float: left
      .back-icon
        text-align: center
        font-soze: .4rem
    .header-input
      flex: 1
      height: .62rem // .86 - .12 - .12
      line-height: .62rem // .86 - .12 - .12
      margin-top: .12rem
      margin-left: .2rem
      padding-left: .2rem
      background: #fff
      border-radius: .1rem
      color: #ccc
    .header-right
      min-width: 1.24rem
      padding: 0 .1rem
      float: right
      text-align: center
      color: #fff
      .arrow-icon
        margin-left: -.04rem // move slightly to the left as there are 2px spacing between inline-blocks
        font-size: .24rem
</style>
