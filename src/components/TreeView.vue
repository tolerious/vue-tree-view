<template>
  <div class="">
    <ul v-for="td in treeData">
      <!--<span v-if="td.children.length>0" class="fa fa-sort-down">{{td.name}}</span>-->
      <!--<span v-else>{{td.name}}</span>-->
      <span v-if="td.children.length>0" class="fa fa-sort-down" @click="handleCollapse(td)"></span>
      <span v-else class="fa fa-sort-down" style="opacity: 0;"></span>
      <span>{{td.name}}</span>
      <li v-show="isShow" :class="classObject">
        <tree-view :treeData="td.children"></tree-view>
      </li>
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
      handleCollapse: function (da) {
        console.log('handle...')
        console.log(this.treeData.length)
        console.log(da.name)
      }
    },
    components: {}
  }
</script>
