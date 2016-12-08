<template>
  <li @dblclick.stop="editItem">
    <span v-if="isFloder" class="fa fa-caret-down"></span>
    <span :class="{inputShow:inputHide,inputHide:inputShow}">{{data.name}}</span>
    <input v-model="name" :class="{inputShow:inputShow,inputHide:inputHide}">
    <span class="fa fa-trash" @click="deleteItem"></span>
    <slot name="childTreeComponent"></slot>
  </li>
</template>
<style>
  .inputShow {
    display: inline-block;
  }

  .inputHide {
    display: none;
  }

  span {
    line-height: 17px;
  }

  input {
    line-height: 23px;
    height: 23px;
    font-size: 14px;
  }
</style>
<script>
  export default{
    props: ['data'],
    computed: {
      isFloder: function () {
        return this.data.children.length > 0 && this.data.children
      },
      name: function () {
        return this.data.name
      }
    },
    data () {
      return {
        inputShow: false,
        inputHide: true
      }
    },
    components: {},
    methods: {
      deleteItem: function () {
        console.log('delete...')
        this.$emit('delete-item', this.data)
      },
      editItem: function () {
        this.inputShow = true
        this.inputHide = false
      }
    }
  }
</script>
