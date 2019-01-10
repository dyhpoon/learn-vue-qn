<template>
  <div class="wrapper">
    <swiper :options="swiperOption">
      <swiper-slide v-for="item of swiperList" :key="item.id">
        <img class="swiper-img" :src="item.image" />
      </swiper-slide>
      <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true,
        autoplay: false
      },
      swiperList: [
        {
          id: 1,
          image: '//img1.qunarzz.com/sight/p0/1607/7c/7cda8b6782dabd80b4.img.jpg_600x330_8572a930.jpg'
        },
        {
          id: 2,
          image: '//img1.qunarzz.com/sight/p0/1603/97/97a91e052b51aa9890.water.jpg_600x330_6c2afdc5.jpg'
        }
      ]
    }
  }
}
</script>

<style lang="stylus" scoped>
  // fix global css first
  .wrapper >>> .swiper-pagination-bullet-active
    background: #fff

  .wrapper
    // the following css is to fix incorrect position before/after image is loaded (ex: slow 3G network)
    width: 100%
    overflow: hidden
    height: 0
    padding-bottom: 55% // intrinsic image height/intrinsic image width = 330/600

    /** or you can write the following, but not all browsers support this
    width: 100%
    height: 31.25vw
    */

    // styles
    background: eee

    .swiper-img
      width: 100% // fix oversized image
</style>
