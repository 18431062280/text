<template>
  <div>
      <detai-banner></detai-banner>
      <detai-header></detai-header>
      <div class="content"></div>
  </div>
</template>

<script>
import DetaiBanner from './commponents/Banner'
import DetaiHeader from './commponents/Header'
export default {
    name:'Detail',
    components:{
      DetaiBanner,
      DetaiHeader
    }
    
}
</script>

<style lang="stylus" scoped>
.content
  height: 50rem

</style>