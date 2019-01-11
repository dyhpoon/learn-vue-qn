<template>
  <div>
    <home-header :city="city"/>
    <home-swiper :list="swiperList" />
    <home-icons :list="iconList" />
    <home-recommend :list="recommendList" />
    <home-weekend :list="weekendList" />
  </div>
</template>

<script>
import HomeHeader from './components/Header'
import HomeSwiper from './components/Swiper'
import HomeIcons from './components/Icons'
import HomeRecommend from './components/Recommend'
import HomeWeekend from './components/Weekend'
import axios from 'axios'

export default {
  name: 'Home',
  components: {
    HomeHeader,
    HomeSwiper,
    HomeIcons,
    HomeRecommend,
    HomeWeekend
  },
  mounted () {
    this.getHomeInfo()
  },
  data () {
    return {
      city: '',
      swiperList: [],
      iconList: [],
      recommendList: [],
      weekendList: []
    }
  },
  methods: {
    getHomeInfo () {
      axios.get('/api/home.json')
        .then(res => {
          const data = res.data.data
          this.city = data.city
          this.swiperList = data.swiper_list
          this.iconList = data.icon_list
          this.recommendList = data.recommend_list
          this.weekendList = data.weekend_list
        })
    }
  }
}
</script>

<style>
</style>
