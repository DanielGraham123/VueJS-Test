<template>
  <v-app>
    <div>
      <v-toolbar dark prominent src="https://cdn.vuetifyjs.com/images/backgrounds/vbanner.jpg">
        <v-app-bar-nav-icon></v-app-bar-nav-icon>

        <v-toolbar-title>Axios Test</v-toolbar-title>

        <v-spacer></v-spacer>

        <v-btn icon>
          <v-icon>mdi-export</v-icon>
        </v-btn>
      </v-toolbar>
    </div>

    <v-content>
      <router-view></router-view>

      <items></items>

    </v-content>
    
  </v-app>
</template>

<script>

import Items from "./components/Items";

export default {
  name: 'App',

  components: {
    'items': Items,
  },

  data: () => ({
    //
  }),
};
</script>
