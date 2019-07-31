<template>
  <v-app>
    <v-app-bar app>
      <v-toolbar-title class="headline text-uppercase">
        <span class="font-weight-light"><router-link class="app-bar-link" :to="{ name: 'home', params: {} }">Space Trucker</router-link></span>
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn to="hangar" text small>Hangar</v-btn>
      <div v-if="userId" class="ml1 pointer black" @click="logout()">logout</div>
      <router-link v-else to="/login" class="ml1 no-underline black">login</router-link>
      <v-btn
        text
        href="https://github.com/vuetifyjs/vuetify/releases/latest"
        target="_blank"
      >
        <span class="mr-2">Latest Release</span>
      </v-btn>
    </v-app-bar>

    <v-content>
      <router-view/>
    </v-content>
  </v-app>
</template>

<script>
import HelloWorld from './components/HelloWorld';
import { GC_USER_ID, GC_AUTH_TOKEN } from './constants/settings'

export default {
  name: 'App',
  computed: {
    userId () {
      return this.$root.$data.userId
    }
  },
  components: {
    HelloWorld,
  },
  data: () => ({
    //
  }),
  methods: {
    logout () {
      localStorage.removeItem(GC_USER_ID)
      localStorage.removeItem(GC_AUTH_TOKEN)
      this.$root.$data.userId = localStorage.getItem(GC_USER_ID)
    }
  }
};
</script>

<style>
.app-bar-link {
  text-decoration: none;
}
</style>
