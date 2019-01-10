<template>
  <div>
    <div class="title">Recommendations</div>
    <ul>
      <li class="item border-bottom" v-for="item of recommendList" :key="item.id">
        <img class="item-img" :src="item.image" />

        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.description}}</p>
          <button class="item-button">View Details</button>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeRecommend',
  data () {
    return {
      recommendList: [
        {
          id: 1,
          image: 'http://img1.qunarzz.com/sight/p0/1801/4e/4ee5653be58dcb1a3.water.jpg_200x200_d169685d.jpg',
          title: 'Hong Kong Disneyland',
          description: 'Special Springtime Offer Up to 30% discount for Kingdom Club Rooms'
        },
        {
          id: 2,
          image: 'http://img1.qunarzz.com/sight/p0/1811/42/42958b9abc760e2aa3.img.jpg_200x200_09b6d404.jpg',
          title: 'Sanya historic scene area',
          description: 'all the year round with li and miao New Year big temple fair, hc section, water-sprinkling festival, chinese-style chest covering, masks and other activities, are very popular with tourists, is an ideal destination to sanya vigil.'
        },
        {
          id: 3,
          image: 'http://img1.qunarzz.com/sight/p0/201405/27/ef08b0cb4a5afb2f570e5c4dff5f743e.jpg_200x200_f3ad8918.jpg',
          title: 'Chimelong International Circus',
          description: 'Guangzhou Chimelong International Circus will be ushering in the festival with a special themed event'
        },
        {
          id: 4,
          image: 'http://img1.qunarzz.com/sight/p0/1809/ff/ffc62d609a5c3521a3.img.jpg_200x200_40c7c1e0.jpg',
          title: 'Yalong Bay Tropical Paradise Forest Park',
          description: 'Surround the National Hoilday Resort of Yalong, leveled on world-class eco-resort coast mountain forest with various species, unique geographic structure, abundant water resources and colorful folk culture.'
        }
      ]
    }
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
