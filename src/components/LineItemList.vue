<template>
  <div>
    <p>lineitem lsit</p>
    <line-item 
      v-for="(item, index) in items" 
      v-bind:yearly="item"
      v-on:changeyear="$set(items, index, $event)"
    ></line-item>
    <line-total 
      v-bind:items="items"
    ></line-total>

    <button v-on:click="addtem">+</button>
  </div>
</template>

<script>
  import LineItem from './LineItem'
  import LineTotal from './LineTotal'
  export default {
    data () {
      return {
        items: []
      }
    },
    components: {
      'line-item': LineItem,
      'line-total': LineTotal
    },
    methods: {
      addtem () {
        this.items.push(0)
      }
    }
  }
</script>

<style>

</style>
