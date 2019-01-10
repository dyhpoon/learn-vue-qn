<template>
  <div class="header">
    <div class="header-left">
      <div class="iconfont back-icon">&#xe624;</div>
    </div>
    <div class="header-input">
      <span class="iconfont">&#xe632;</span>
      Cities/Places
      </div>
    <div class="header-right">
      Cities
      <span class="iconfont arrow-icon">&#xe64a;</span>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HomeHeader'
}
</script>

<style lang="stylus" scoped>
  @import '~@styles/variables.styl';
  .header
    display: flex
    line-height: .86rem // html font-size is 50px, height is 86px@2x (43px@1x)
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
      width: 1.24rem
      float: right
      text-align: center
      .arrow-icon
        margin-left: -.04rem // move slightly to the left as there are 2px spacing between inline-blocks
        font-size: .24rem
</style>
