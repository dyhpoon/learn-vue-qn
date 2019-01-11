<template>
  <div class="search">
    <input class="search-input" type="text" placeholder="City/Place">
  </div>
</template>

<script>
export default {
  name: 'CitySearch'
}
</script>

<style lang="stylus" scoped>
  @import '~@styles/variables.styl'
  .search
    height: .72rem
    padding: 0 .1rem
    background: $bgColor

    .search-input
      width: 100%
      padding: 0 0.2rem
      height: .62rem
      line-height: .62rem
      border-radius: .06rem
      box-sizing: border-box // if border-box is not set, the width will not be 100% becoz of the padding we added above
      color: #666
</style>
