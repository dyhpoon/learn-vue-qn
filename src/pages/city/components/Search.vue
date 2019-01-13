<template>
  <div>
    <div class="search">
      <input v-model="keyword" class="search-input" type="text" placeholder="City/Place">
    </div>
    <div v-show="keyword" class="search-content" ref="search">
      <ul>
        <li class="search-item border-bottom" v-for="item of list" :key="item.id">{{item.name}}</li>
        <li v-show="hasNoData" class="search-item border-bottom">Not found</li>
      </ul>
    </div>
  </div>
</template>

<script>
import Bscroll from 'better-scroll'
export default {
  name: 'CitySearch',
  props: {
    cities: Object
  },
  data () {
    return {
      keyword: '', // use v-model to do double binding
      list: [],
      timer: null
    }
  },
  computed: {
    hasNoData () {
      return !this.list.length
    }
  },
  watch: {
    keyword () {
      if (this.timer) {
        clearTimeout(this.timer)
      }
      if (!this.keyword) {
        this.list = []
      } else {
        this.timer = setTimeout(() => {
          const result = []
          for (let i in this.cities) {
            this.cities[i].forEach(value => {
              if (value.name.indexOf(this.keyword.toLowerCase()) > -1) {
                result.push(value)
              }
            })
          }
          this.list = result
        }, 100)
      }
    }
  },
  mounted () {
    this.scroll = new Bscroll(this.$refs.search)
  }
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

  .search-content
    z-index: 1
    position: absolute
    top: 1.58rem
    left: 0
    right: 0
    bottom: 0
    background: #eee
    .search-item
      line-height: .62rem
      padding-left: .2rem
      background: #fff
      color: #666
</style>
