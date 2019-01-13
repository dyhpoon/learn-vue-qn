<template>
  <div>
    <city-header />
    <city-search :cities="cities" />
    <city-list :cities="cities" :hot="hotCities" :letter="letter" />
    <city-alphabet :cities="cities" @changeOnLetter="handleLetterClicked" />
  </div>
</template>

<script>
import axios from 'axios'
import CityHeader from './components/Header'
import CitySearch from './components/Search'
import CityList from './components/List'
import CityAlphabet from './components/Alphabet'
export default {
  name: 'City',
  components: {
    CityHeader,
    CitySearch,
    CityList,
    CityAlphabet
  },
  mounted () {
    this.getCityInfo()
  },
  data () {
    return {
      cities: {},
      hotCities: [],
      letter: ''
    }
  },
  methods: {
    getCityInfo () {
      axios.get('/api/city.json')
        .then(res => {
          const data = res.data.data
          this.cities = data.cities
          this.hotCities = data.hotCities
        })
    },
    handleLetterClicked (letter) {
      this.letter = letter
    }
  }
}
</script>

<style lang="stylus" scoped>

</style>
