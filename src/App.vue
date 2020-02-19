<template>
  <v-app>
    <v-app-bar
      app
      color="primary"
      dark
      dense
    >
      <div class="d-flex align-center">
        Coby Yates Portfolio
      </div>

      <v-spacer></v-spacer>
    </v-app-bar>

    <v-content>
      <Home/>
    </v-content>
  </v-app>
</template>

<script>
import Home from './components/Home';

export default {
  name: 'App',

  components: {
    Home,
  },

  created () {
      this.$vuetify.theme.dark = true
    },

  data: () => ({
    //
  }),
};
</script>
