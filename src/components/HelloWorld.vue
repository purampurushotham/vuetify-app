<template>
  <v-container grid-list-xl pa-0>
    <v-layout row wrap justify-center>
      <v-flex xs12 sm6 md4 d-flex>

      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>

export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
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
