<template>
  <v-app>
    <Header></Header>
    <v-main>
      <router-view />
    </v-main>
  </v-app>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import Home from "./views/Home.vue";
import Header from "./views/Header.vue";

@Component({
  components: {
    Home,
    Header,
  },
})
export default class App extends Vue {}
</script>

<style lang="scss">
.v-main {
  background-color: #f4f3f3;
}
</style>
