<template>
 <table>
  <tr>
    <td>{{ getYearTotal().toFixed(2) }}</td>
    <td>{{ (getYearTotal() / 12).toFixed(2) }}</td>
    <td>{{ (getYearTotal() / 52).toFixed(2) }}</td>
    <td>{{ (getYearTotal() / 365).toFixed(2) }}</td>
  </tr>
 </table>

</template>

<script>
  export default {
    props: [ 'items' ],
    methods: {
      getYearTotal () {
        var sum = 0
        for (var i = 0; i < this.items.length; i++) {
          sum += this.items[i]
        }
        return sum
      }
    }
  }
</script>

<style>
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

table {
  width: 70%;
  margin: 0 auto; 
}

td {
  width: 115px;
}
a {
  color: #42b983;
}
</style>
