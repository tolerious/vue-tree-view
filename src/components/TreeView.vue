<template>
  <div class="">
    <ul v-for="td in treeData">
      <!--<span v-if="td.children.length>0" class="fa fa-sort-down">{{td.name}}</span>-->
      <!--<span v-else>{{td.name}}</span>-->
      <span v-if="td.children.length>0" class="fa fa-sort-down" @click="handleCollapseItem(td)"></span>
      <span v-else class="fa fa-sort-down" style="opacity: 0;"></span>
      <span>{{td.name}}</span>
      <span class="fa fa-trash-o" @click="handleDeleteItem"></span>
      <span class="fa fa-plus" v-show="td.children.length>0"></span>

      <!--<li v-show="isShow" :class="classObject">-->
      <tree-view :treeData="td.children"></tree-view>
      <!--</li>-->
    </ul>
  </div>
</template>
<style>
  ul, li {
    list-style: none;
  }

  span {
    text-align: center;
  }
</style>
<script>
  export default{
    name: 'tree-view',
    props: ['treeData'],
    mounted: function () {
      this.$nextTick(function () {
        console.log('tick...')
      })
    },
    data () {
      return {
        isShow: true,
        classObject: {
          animated: false,
          lightSpeedOut: false
        },
        collapse: 'block'
      }
    },
    computed: {
      isFolder: function () {
        console.log(this.treeData)
        if (this.treeData.length > 1) {
          return true
        } else {
          return false
        }
      }
    },
    methods: {
      handleCollapseItem: function (da) {
        console.log('handle...')
        console.log(this.treeData.length)
        console.log(da.name)
        console.log(da.children)
      },
      handleDeleteItem: function () {
        console.log('delete item...')
      }
    },
    components: {}
  }
</script>
