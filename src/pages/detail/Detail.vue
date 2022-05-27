<template>
  <div>
      <detai-banner></detai-banner>
      <detai-header></detai-header>
      <div class="content">
        <detai-list :list="list"></detai-list>
      </div>
  </div>
</template>

<script>
import DetaiBanner from './commponents/Banner'
import DetaiHeader from './commponents/Header'
import DetaiList from './commponents/List'
export default {
    name:'Detail',
    components:{
      DetaiBanner,
      DetaiHeader,
      DetaiList
    },
    data() {
      return{
        list: [{
          title: '成人票',
          children: [{
            title:'成人三管联票',
            children: [{
              title:'成人三管联票-连锁店',
            }]
          },{
            title:'成人五管联票'
          }]
        },{
          title: '学生票'
        },{
          title: '儿童票'
        },{
          title: '特惠票'
        }]

      }
    }
    
}
</script>

<style lang="stylus" scoped>
.content
  height: 50rem

</style>