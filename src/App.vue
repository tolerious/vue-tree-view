<template>
  <div id="app">
    <img src="./assets/logo.png">
    <tree-view :treeData="treeData"></tree-view>
  </div>
</template>
<style>
  body, html {
    font-size: 14px;
  }
  ul,li {
    font-size: 14px;
  }
</style>
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
                  name: '第一章第一小节第一小段第一小天地',
                  children: []
                },
                {
                  name: '第一章第一小节第一小段第二小天地',
                  children: []
                }
              ]
            },
            {
              name: '第一章第一小节第二小段',
              children: [
                {
                  name: '第一章第一小节第二小段第一小天地',
                  children: []
                }
              ]
            }
          ]
        },
        {
          name: '第一章第二小节',
          children: [
            {
              name: '第一章第二小节第一小段',
              children: []
            },
            {
              name: '第一章第二小节第二小段',
              children: []
            }
          ]
        }
      ]
    },
    {
      name: '第二章',
      children: [
        {
          name: '第二章第一小节',
          children: []
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
    },
    methods: {}
  }
</script>

<style>
</style>
