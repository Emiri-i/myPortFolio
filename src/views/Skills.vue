<template>
  <div>
    <v-container>
      <h1 class="text-center page-title">- Skills -</h1>
      <v-card flat style="background: white" class="mt-5">
        <v-container>
          <div class="text-center mb-3" style="font-size: 2.5em">
            <span class="title-color"> coding language </span>
          </div>
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
      </v-card>
      <v-card flat class="mt-10" style="background: white">
        <v-container>
          <div class="text-center mb-3" style="font-size: 2.5em">
            <span class="title-color"> languages </span>
          </div>
          <v-row>
            <v-col cols="12" class="pb-0">
              <div class="d-flex justify-center">Japanese: Native</div>
            </v-col>
            <v-col cols="12" class="pt-0">
              <div class="d-flex justify-center">
                English: Advanced/Business
              </div>
            </v-col>
          </v-row>
        </v-container>
      </v-card>
      <v-card flat class="mt-10" style="background: white">
        <v-container>
          <div class="text-center mb-3" style="font-size: 2.5em">
            <span class="title-color"> tools </span>
          </div>
          <v-row>
            <v-col cols="4">
              <div class="d-flex justify-center">
                <v-icon x-large>mdi-microsoft-visual-studio-code</v-icon>
              </div>
              <div class="d-flex justify-center">Visual Studio Code</div>
            </v-col>
            <v-col cols="4">
              <div class="d-flex justify-center">
                <v-icon x-large>mdi-github</v-icon>
              </div>
              <div class="d-flex justify-center">git</div>
            </v-col>
            <v-col cols="4">
              <div class="d-flex justify-center">
                <v-icon x-large>mdi-firebase</v-icon>
              </div>
              <div class="d-flex justify-center">firebase</div>
            </v-col>
          </v-row>
        </v-container>
      </v-card>
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
.title-color {
  color: #7f7c82;
  border-bottom: double 5px #f0d9ff;
}
</style>
