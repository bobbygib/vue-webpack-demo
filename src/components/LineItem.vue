<template>
  <div class="money">
    <li>Year: 
      <input 
        type="number" 
        v-on:change="change_year" 
        v-bind:value="(+yearly).toFixed(2)"
      ></li>
    <li>Month: 
      <input 
        type="number" 
        v-on:change="change_month" 
        v-bind:value="(+yearly / 12).toFixed(2)"
      ></li>
    <li>Week: 
      <input 
        type="number" 
        v-on:change="change_week" 
        v-bind:value="(+yearly / 52).toFixed(2)"
      ></li>
    <li>Day: 
      <input 
        type="number" 
        v-on:change="change_day" 
        v-bind:value="(+yearly / 365).toFixed(2)"
    ></li>
    
  </div>
</template>

<script>
export default {
  name: 'money',
  // data () {
  //   return {
  //     yearly: 0
  //   }
  // },
  props: [ 'yearly' ],
  methods: {
    change_year (evt) {
      this.$emit('changeyear', evt.target.value * 1)
    },
    change_month (evt) {
      this.$emit('changeyear', evt.target.value * 12)
    },
    change_week (evt) {
      this.$emit('changeyear', evt.target.value * 52)
    },
    change_day (evt) {
      this.$emit('changeyear', evt.target.value * 365)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
