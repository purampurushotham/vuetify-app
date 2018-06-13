<template>
  <div id="app">
    <v-app>
      <v-navigation-drawer
                           persistent
                           :mini-variant="miniVariant"
                           :clipped="clipped"
                           v-model="drawer"
                           fixed
                           app
                           :right="right"
      >
        <v-list>
          <v-list-tile
            value="true"
            v-for="(item, i) in items"
            :key="i"
            :to="item.route"
          >
            <v-list-tile-action>
              <v-icon v-html="item.icon"></v-icon>
            </v-list-tile-action>
            <v-list-tile-content>
              <v-list-tile-title v-text="item.title"></v-list-tile-title>
            </v-list-tile-content>
          </v-list-tile>
        </v-list>
      </v-navigation-drawer>
      <v-toolbar
        app
        :clipped-left="clipped"
        :right = "right"
      >
        <v-toolbar-side-icon @click.stop="drawer = !drawer"></v-toolbar-side-icon>
        <v-btn icon @click.stop="miniVariant = !miniVariant">
          <v-icon v-html="miniVariant ? 'chevron_right' : 'chevron_left'"></v-icon>
        </v-btn>
        <v-btn icon @click.stop="clipped = !clipped">
          <v-icon>web</v-icon>
        </v-btn>
        <v-btn icon @click.stop="fixed = !fixed">
          <v-icon>remove</v-icon>
        </v-btn>
        <v-toolbar-title v-text="title"></v-toolbar-title>
      </v-toolbar>
      <v-jumbotron active-class = "default-class">
<v-container fill-height>
  <v-layout align-center>
    <v-flex text-xs-center>
      <h3 class="display-3">My jumnbotron</h3>
      <v-container grid-list-md>
        <v-layout row wrap>
          <v-flex xs12 md4 >
          </v-flex>
          <v-flex xs12 md4>
            <v-text-field v-model="search_string" solo label="Search" :append-icon-cb = "searchEvent" append-icon="home"></v-text-field>
          </v-flex>
          <v-flex xs12 md4>
          </v-flex>
        </v-layout>
      </v-container>
    </v-flex>
  </v-layout>
</v-container>
      </v-jumbotron>
        <v-content app wrap>
          <router-view/>
        </v-content>
    </v-app>
  </div>
</template>
<script>
export default {
  name: 'App',
  data () {
    return {
      drawer: false,
      clipped: false,
      miniVariant: false,
      right: true,
      items: [{
        icon: 'bubble_chart',
        title: 'Inspire',
        route: '/hello'
      }],
      title: 'Vuetify.js',
      search_string: ''
    }
  },
  methods: {
    searchEvent (event) {
      var vm = this
      console.log(vm.search_string)
    }
  }
}

</script>
<style>
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  }
</style>
