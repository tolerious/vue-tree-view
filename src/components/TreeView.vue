<template>
  <div>
    <ul v-for="td in treeData">
      <li>
        <span>{{td.name}}</span>
        <tree-view :treeData="td.children"></tree-view>
      </li>
    </ul>
  </div>
</template>
<style>
</style>
<script>
  export default{
    name: 'tree-view',
    props: ['treeData'],
    data () {
      return {}
    },
    methods: {
      abc: function () {

      }
    },
    components: {}
  }
</script>
