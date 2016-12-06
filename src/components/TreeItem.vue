<template>
  <li>
    <span v-if="isFloder" class="fa fa-caret-down">{{data.name}}</span>
    <span v-else>{{data.name}}</span>
    <span class="fa fa-trash" @click="handleDeleteItem"></span>
    <slot name="childTreeComponent"></slot>
  </li>
</template>
<style>
</style>
<script>
  export default{
    props: ['data'],
    computed: {
      isFloder: function () {
        return this.data.children.length > 0 && this.data.children
      }
    },
    data () {
      return {}
    },
    components: {},
    methods: {
      handleDeleteItem: function () {
        console.log('delete...')
      }
    }
  }
</script>
