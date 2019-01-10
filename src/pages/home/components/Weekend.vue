<template>
  <div>
    <div class="title">Where to go on weekend?</div>
    <ul>
      <li class="item border-bottom" v-for="item of recommendList" :key="item.id">
        <div class="item-img-wrapper">
          <img class="item-img" :src="item.image" />
        </div>

        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.description}}</p>
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
          image: 'http://img1.qunarzz.com/sight/source/1510/6e/1ea71e2f04e.jpg_r_640x214_aa6f091d.jpg',
          title: 'Beijing\'s Top Hot Springs',
          description: 'Spending a few hours at a hot spring is a great way to relax and rejuvenate.'
        },
        {
          id: 2,
          image: 'http://img1.qunarzz.com/sight/source/1505/aa/7baaf8a851d221.jpg_r_640x214_1431200f.jpg',
          title: 'Top 10 Must See Places in Beijing',
          description: 'You should make sure to get around the top ten places in Beijing City. In this way, you can say that you have been to Beijing City!'
        },
        {
          id: 3,
          image: 'http://img1.qunarzz.com/sight/source/1505/9e/21df651e19af5d.jpg_r_640x214_3ea5bb38.jpg',
          title: 'The Imperial City',
          description: 'It is a section of the city of Beijing in the Ming and Qing dynasties, with the Forbidden City at its center.'
        },
        {
          id: 4,
          image: 'http://img1.qunarzz.com/sight/source/1505/ce/bc89bc2f0e33ea.jpg_r_640x214_3e408453.jpg',
          title: 'Best Cultural Museums in Beijing',
          description: 'Millions of words have been written ruminating on the idea of \'culture\' – what it is, what it means, why it matters – but, broadly defined, it\'s the stuff that makes up the rich fabric of human civilisation.'
        },
        {
          id: 5,
          image: 'http://img1.qunarzz.com/sight/source/1505/b2/fde1bfcd057a52.jpg_r_640x214_bbf3fa44.jpg',
          title: "Beijing Aquarium",
          description: 'Beijing Aquarium is the largest and most advanced inland aquarium in China, covering a total area of 30 acres.'
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

  .item-img-wrapper
    overflow: hidden
    height: 0
    padding-bottom: 33.9%
    .item-img
      width: 100%

  .item-info
    padding: .1rem
    .item-title
      line-height: .54rem
      font-size: .32rem
      ellipsis() // if text is too long
    .item-desc
      line-height: .4rem
      color: #ccc
      ellipsis() // if text is too long
</style>
