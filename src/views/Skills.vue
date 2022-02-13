<template>
  <div>
    <v-container>
      <h1
        class="text-center"
        style="font-family: cursive; color: #bfa2db; font-size: 3.5em"
      >
        - Skills -
      </h1>
      <v-card flat style="background: white">
        <div class="coding-lang mt-5">
          <div class="text-center" style="font-size: 2.5em">
            coding language
          </div>
          <v-container>
            <v-row class="mt-0">
              <v-col cols="4" sm="2">
                <div class="d-flex justify-center">
                  <v-icon x-large>mdi-vuejs</v-icon>
                </div>
                <div class="d-flex justify-center">Vue.js</div>
              </v-col>
              <v-col cols="4" sm="2">
                <div class="d-flex justify-center">
                  <v-icon x-large>mdi-vuetify</v-icon>
                </div>
                <div class="d-flex justify-center">vuetify</div>
              </v-col>
              <v-col cols="4" sm="2">
                <div class="d-flex justify-center">
                  <v-icon x-large>mdi-language-javascript</v-icon>
                </div>
                <div class="d-flex justify-center">Javascript</div>
              </v-col>
              <v-col cols="4" sm="2">
                <div class="d-flex justify-center">
                  <v-icon x-large>mdi-language-typescript</v-icon>
                </div>
                <div class="d-flex justify-center">typescript</div>
              </v-col>
              <v-col cols="4" sm="2">
                <div class="d-flex justify-center">
                  <v-icon x-large>mdi-language-html5</v-icon>
                </div>
                <div class="d-flex justify-center">HTML</div>
              </v-col>
              <v-col cols="4" sm="2">
                <div class="d-flex justify-center">
                  <v-icon x-large>mdi-language-css3</v-icon>
                </div>
                <div class="d-flex justify-center">CSS</div>
              </v-col>
              <v-col cols="4" sm="2">
                <div class="d-flex justify-center">
                  <v-icon x-large>mdi-salesforce</v-icon>
                </div>
                <div class="d-flex justify-center">Apex</div>
              </v-col>
              <v-col cols="4" sm="2">
                <div class="d-flex justify-center">
                  <v-icon x-large>mdi-salesforce</v-icon>
                </div>
                <div class="d-flex justify-center">Visualforce</div>
              </v-col>
            </v-row>
          </v-container>
        </div>
      </v-card>
      <!-- <v-divider></v-divider>
      <div class="tools">tools</div>
      <v-divider></v-divider>
      <div class="language">language</div> -->
    </v-container>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
@Component({
  components: {},
})
export default class Skills extends Vue {
  codingLanguageList: any[] = [
    { name: "Vue.js", icon: "mdi-vuejs" },
    { name: "Vuetify", icon: "mdi-vuetify" },
    { name: "Javascript", icon: "mdi-language-javascript" },
    { name: "Typescript", icon: "mdi-language-typescript" },
    { name: "HTML", icon: "mdi-language-html5" },
    { name: "CSS", icon: "mdi-language-css3" },
    { name: "Apex,Visualforce", icon: "mdi-salesforce" },
  ];
}
</script>
<style lang="scss">
.coding-lang {
  color: #7f7c82;
}
</style>
