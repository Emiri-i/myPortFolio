<template>
  <div class="about">
    <div>
      <v-container>
        <h1 class="text-center page-title">- About me -</h1>
        <v-scroll-y-transition mode="in">
          <v-row class="mt-5" v-show="isShow">
            <v-col cols="12" sm="3" class="d-flex align-center justify-center">
              <v-img src="../libs/F.jpg" style="max-width: 200px"></v-img>
            </v-col>
            <v-col cols="12" sm="9">
              <div class="pl-6 about-me-sentence" style="font-size: 1.25em">
                <div style="font-size: 2em" class="typing">
                  Hi, I'm Emiri.
                  <!-- <strong class="typing">Hi, I'm Emiri.</strong> -->
                </div>
                <div>
                  <strong class="underline">a Frontend-developer</strong>
                  from Japan.
                </div>
                <div class="mt-4">
                  I have
                  <strong class="underline"
                    >3 years developer experience</strong
                  >
                  in total, including Salesforce developer and current
                  Frotnend-developer role.
                </div>
                <div class="mt-4">
                  Not only Frontend-Develoeper, but also currently in charge of
                  UI design. I enjoy having responsibilities for both creating
                  UI that I envision and giving them shape by coding.
                </div>
                <div class="mt-4">
                  I am
                  <strong class="underline">
                    motivated, open-minded, a hard worker, and have the ability
                    to work cross-functionally.
                  </strong>
                  Besides that, I also have experience working internationally,
                  so I can easily adjust myself to new environments and love new
                  challenges.
                </div>
              </div>
            </v-col>
          </v-row>
        </v-scroll-y-transition>
      </v-container>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
@Component({
  components: {},
})
export default class AboutMe extends Vue {
  isShow: boolean = false;
  created() {
    this.$nextTick(() => {
      this.isShow = true;
    });
  }
}
</script>

<style lang="scss">
.v-image {
  box-shadow: 20px 20px 0 #f0d9ff;
  margin-bottom: 20px; //centering
  margin-right: 20px; //centering
}
.about-me-sentence {
  color: #7f7c82;
}
.typing {
  display: inline-block;
  width: 10ch;
  overflow: hidden;
  white-space: nowrap;
  white-space: nowrap;
  overflow: hidden;
  border-right: 3px solid;
  animation: typing 2s steps(14), blink 1.2s infinite;
}
.underline {
  background: linear-gradient(transparent 70%, #fff176 0%);
}
@keyframes typing {
  from {
    width: 0; // 行頭から開始
  }
}

@keyframes blink {
  50% {
    border-color: transparent;
  }
}
</style>
