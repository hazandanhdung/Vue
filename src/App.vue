<template>
  <v-app>
    <v-toolbar app dark height="50px" class="indigo">
      <v-toolbar-title class="headline text-uppercase">

        <span class="font-weight-light">VUE - UI</span>
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn
        flat
        href="https://github.com/vuetifyjs/vuetify/releases/latest"
        target="_blank"
      >
        <span class="mr-2">version 0.1</span>
      </v-btn>

    </v-toolbar>

    <v-content>
      <HelloWorld/>
    </v-content>
  </v-app>

</template>

<script>
import HelloWorld from './components/HelloWorld'

export default {
  name: 'App',
  components: {
    HelloWorld
  },
  data () {
    return {
      //
    }
  }
}
</script>
