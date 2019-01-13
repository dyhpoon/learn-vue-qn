<template>
  <div>
    <detail-banner />
    <detail-header />
    <div class="content">
      <detail-list :list="list" />
    </div>
  </div>
</template>

<script>
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
      list: [
        {
          title: 'Adult',
          children: [
            {
              title: 'Adult - Day Pass',
            },
            {
              title: 'Adult - Two Day Pass'
            }
          ]
        },
        {
          title: 'Student'
        },
        {
          title: 'Child'
        },
        {
          title: 'Senior'
        }
      ]
    }
  }
}
</script>

<style lang="stylus" scoped>
  .content
    height: 50rem
</style>
