<template>
  <div>
      <city-header></city-header>
      <city-search></city-search>
      <city-list></city-list>
      <city-alphabet></city-alphabet>
  </div>
</template>

<script>

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
    }
}
</script>

<style lang="stylus" scoped>

</style>