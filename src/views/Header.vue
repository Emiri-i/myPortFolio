<template>
  <div>
    <v-app-bar app flat hide-on-scroll color="#f4f3f3">
      <v-spacer></v-spacer>
      <v-btn icon @click="goToLinkedIn">
        <v-icon>mdi-linkedin</v-icon>
      </v-btn>
      <v-app-bar-nav-icon @click="drawer = true"></v-app-bar-nav-icon>
    </v-app-bar>

    <v-navigation-drawer
      v-model="drawer"
      absolute
      temporary
      right
      color="#f4f3f3"
    >
      <v-list nav dense>
        <v-list-item-group
          v-model="navBarGroup"
          active-class="header-active"
          mandatory
        >
          <v-list-item v-for="item in navItems" :key="item.id" :to="item.link">
            <v-list-item-icon class="nav-item">
              <v-icon>{{ item.icon }}</v-icon>
            </v-list-item-icon>
            <v-list-item-title class="nav-item">
              {{ item.title }}
            </v-list-item-title>
          </v-list-item>
        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>
  </div>
</template>

<script lang="ts">
import { Component, Vue, Prop, Watch } from "vue-property-decorator";

@Component({
  components: {},
})
export default class Header extends Vue {
  @Prop({ type: Object, default: {} })
  readonly currentPageInfo?: any;

  drawer: boolean = false;
  navBarGroup: number = 0;
  linkedinURL: string = "https://www.linkedin.com/in/emiri-ishikawa-5579341b0/";
  navItems: any[] = [
    { id: 1, title: "Home", icon: "mdi-home", link: "/" },
    { id: 2, title: "About Me", icon: "mdi-account", link: "/aboutMe" },
    { id: 3, title: "Skills", icon: "mdi-keyboard", link: "/skills" },
    { id: 4, title: "Projects", icon: "mdi-file-multiple", link: "/projects" },
  ];

  @Watch("currentPageInfo")
  onChangepage() {
    console.log("this.currentPageInfo", this.currentPageInfo);
    let targetPageInfo = this.navItems.find(
      (item: any, index: number) => item.link === this.currentPageInfo.link
    );
    this.navBarGroup = targetPageInfo.id - 1;
    console.log("navBarGroup", this.navBarGroup);
  }

  goToLinkedIn() {
    const win = window.open(this.linkedinURL);
    win?.focus();
  }
}
</script>

<style lang="scss">
.header-active {
  background-color: #f0d9ff;
  > .v-list-item__title,
  .v-list-item__icon {
    color: #aa14f0 !important;
  }
}
.nav-item {
  color: #757575;
}
</style>
