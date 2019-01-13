<template>
  <div>
    <detail-banner :place="place" :banner="banner" :galleryImages="galleryImages" />
    <detail-header />
    <div class="content">
      <detail-list :list="list" />
    </div>
  </div>
</template>

<script>
import axios from 'axios'
import DetailBanner from './components/Banner'
import DetailHeader from './components/Header'
import DetailList from './components/List'
export default {
  name: 'Detail',
  components: {
    DetailBanner,
    DetailHeader,
    DetailList
  },
  data () {
    return {
      place: '',
      banner: '',
      galleryImages: [],
      list: []
    }
  },
  methods: {
    getDetailInfo () {
      axios.get('/api/detail.json', {
        params: {
          id: this.$route.params.id
        }
      }).then(res => {
        const data = res.data.data
        this.place = data.place
        this.banner = data.banner
        this.galleryImages = data.gallery_images
        this.list = data.category_list
      })
    }
  },
  mounted () {
    this.getDetailInfo()
  }
}
</script>

<style lang="stylus" scoped>
  .content
    height: 50rem
</style>
