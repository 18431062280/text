<template>
  <div>
      <city-header></city-header>
      <city-search></city-search>
      <city-list :cities="cities" :hot="hotCities"></city-list>
      <city-alphabet :cities="cities"></city-alphabet>
  </div>
</template>

<script>
import axios from 'axios'
import CityHeader from './commponents/Header.vue'
import CitySearch from './commponents/Search.vue'
import CityList from './commponents/List.vue'
import CityAlphabet from './commponents/Alphabet.vue'
export default {
    name: 'City',
    components: {
        CityHeader,
        CitySearch,
        CityList,
        CityAlphabet
    },
    data(){
        return{
            cities: {},
            hotCities: []
        }
    },
    methods:{
        getCityInfo(){
            axios.get('/api/city.json')
                .then(this.handleGetCityInfoSucc)
        },
        handleGetCityInfoSucc(res){
            console.log(res)
            res = res.data
            if(res.ret && res.data){
                const data = res.data 
                this.cities =data.cities
                this.hotCities = data.hotCities
            }
        }
    },
    mounted() {
        this.getCityInfo()
    }
}
</script>

<style lang="stylus" scoped>

</style>