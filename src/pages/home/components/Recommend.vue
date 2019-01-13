<template>
  <div>
    <div class="title">Recommendations</div>
    <ul>
      <router-link tag="li" :to="`/detail/${item.id}`" class="item border-bottom" v-for="item of list" :key="item.id">
        <img class="item-img" :src="item.image" />

        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.description}}</p>
          <button class="item-button">View Details</button>
        </div>
      </router-link>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeRecommend',
  props: {
    list: Array
  }
}
</script>

<style lang="stylus" scoped>
  @import '~@styles/mixin.styl'

  .title
    margin-top: .2rem
    line-height: .8rem
    background: #eee
    text-indent: .2rem

  .item
    display: flex
    height: 1.9rem
    overflow: hidden

    .item-img
      width: 1.7rem
      height: 1.7rem
      padding: .1rem

    .item-info
      flex: 1
      padding: .1rem
      min-width: 0 //!! fix ellipsis not showing

      .item-title
        line-height: .54rem
        font-size: .32rem
        ellipsis() // if text is too long
      .item-desc
        line-height: .4rem
        color: #ccc
        ellipsis() // if text is too long
      .item-button
        line-height: .44rem
        margin-top: 0.16rem
        background: #ff9300
        padding: 0 .2rem
        border-radius: .06rem
        color: #fff
</style>
