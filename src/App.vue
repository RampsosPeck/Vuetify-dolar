<template>
  <v-app>
    <v-app-bar app>
      <v-toolbar-title class="headline text-uppercase">
        <span>Vuetify</span>
        <span class="font-weight-light">MATERIAL DESIGN</span>
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn
        text
        href="https://github.com/vuetifyjs/vuetify/releases/latest"
        target="_blank"
      >
        <span class="mr-2">Latest Release</span>
        <v-icon>open_in_new</v-icon>
      </v-btn>
    </v-app-bar>

    <v-content>
      <HelloWorld/>
      <v-dialog
        v-model="loading.estado"
        hide-overlay
        persistent
        width="300"
      >
        <v-card
          :color="loading.color"
          dark
        >
          <v-card-text>
            {{ loading.titulo }}
            <v-progress-linear
              indeterminate
              color="white"
              class="mb-0"
            ></v-progress-linear>
          </v-card-text>
        </v-card>
      </v-dialog>
    </v-content>
  </v-app>
</template>

<script>
import HelloWorld from './components/HelloWorld';
import {mapState} from 'vuex';
export default {
  name: 'App',
  components: {
    HelloWorld,
  },
  data: () => ({
    //
  }),
  computed:{
    ...mapState(['loading'])
  }
};
</script>
