<template>
  <div id="app">
    <img src="./assets/logo.png">
    <tree-view :treeData="treeData"></tree-view>
  </div>
</template>

<script>
  import Hello from './components/Hello'
  import TreeView from './components/TreeView.vue'
  let data = [
    {
      name: '第一章',
      children: [
        {
          name: '第一章第一小节',
          children: [
            {
              name: '第一章第一小节第一小段',
              children: [
                {
                  name: '第一章第一小节第一小段第一小天地'
                }
              ]
            },
            {
              name: '第一章第一小节第二小段'
            }
          ]
        },
        {
          name: '第一章第二小节'
        }
      ]
    },
    {
      name: '第二章',
      children: [
        {
          name: '第二章第一小节'
        }
      ]
    }
  ]

  export default {
    name: 'app',
    data () {
      return {
        treeData: data
      }
    },
    components: {
      Hello,
      TreeView
    }
  }
</script>

<style>
</style>
