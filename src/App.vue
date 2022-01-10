<template>
  <v-app>
    <Header :current-page-info="currentPageInfo"></Header>
    <v-main>
      <router-view @send="currentPageInfo = $event" />
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
export default class App extends Vue {
  currentPageInfo: any = {};

  // sendCurrentPageInfo(value: any) {
  //   console.log("router", this.$router);
  //   this.$router.push(value.link);
  //   this.currentPageInfo = value;
  // }
}
</script>

<style lang="scss">
.v-main {
  background-color: #f4f3f3;
}
</style>
