<template>
  <ul>
    <draggable element="ul" :list="treeData" @start="dragging=true" @end="dragging=true">
      <tree-item :data="child" v-for="child in treeData">
        <test-tree-view v-if="child.children" slot="childTreeComponent"
                        :treeData="child.children">
        </test-tree-view>
      </tree-item>
    </draggable>
  </ul>
</template>
<style>
  ul, li {
    list-style: none;
  }

  li {
    cursor: pointer;
    margin-bottom: 10px;
  }

  span {
    margin-bottom: 10px;
  }
</style>
<script>
  import draggable from 'vuedraggable'
  import TreeItem from './TreeItem.vue'
  export default{
    name: 'test-tree-view',
    props: ['treeData'],
    mounted: function () {
    },
    data () {
      return {}
    },
    components: {
      TreeItem,
      draggable
    },
    computed: {},
    methods: {}
  }
</script>
