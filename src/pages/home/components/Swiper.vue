<template>
  <div class="wrapper">
    <swiper :options="swiperOption" v-if="showSwiper">
      <swiper-slide v-for="item of list" :key="item.id">
        <img class="swiper-img" :src="item.image" />
      </swiper-slide>
      <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  props: {
    list: Array
  },
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true,
        autoplay: false
      }
    }
  },
  computed: {
    showSwiper () {
      return this.list.length > 0
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
