<template>
  <ul>
    <draggable element="ul" :list="treeData" @start="dragging=true" @end="dragging=true">
      <tree-item :data="child" v-for="child in treeData" @delete-item="deleteItem">
        <tree-view v-if="child.children" slot="childTreeComponent"
                   :treeData="child.children"
        >
        </tree-view>
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
    name: 'tree-view',
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
    methods: {
      deleteItem: function (msg) {
        for (let i = 0; i < this.treeData.length; i++) {
          if (this.treeData[i].name === msg.name) {
            this.treeData.splice(i, 1)
          }
        }
      }
    }
  }
</script>
