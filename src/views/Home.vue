<template>
  <div>
    <v-row>
      <v-col>
        <div class="home-bg">
          <div class="greeting-wrapper">
            <span>H</span>
            <span>e</span>
            <span>l</span>
            <span>l</span>
            <span>o</span>
            <span>!</span>
          </div>
          <div
            style="font-family: Courier New; font-size: 3.25em; color: #f3f1f5"
            class="d-flex justify-center mt-0"
          >
            I am Emiri.
          </div>
          <div
            class="d-flex justify-center mt-0"
            style="color: #f3f1f5; font-size: 1.25em"
          >
            Frontend-developer
          </div>
        </div>
      </v-col>
    </v-row>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
@Component({
  components: {},
})
export default class Home extends Vue {
  timeOut: number = 2000;

  created() {
    this.$nextTick(() => {
      this.setGreetingAnimation();

      setInterval(() => {
        this.setGreetingAnimation();
      }, this.timeOut * 2);
    });
  }

  setGreetingAnimation() {
    const CLASSNAME = "-visible";
    const target = document.getElementsByClassName("greeting-wrapper")[0];
    target.classList.add(CLASSNAME);
    setTimeout(() => {
      target.classList.remove(CLASSNAME);
    }, this.timeOut);
  }
}
</script>

<style lang="scss">
.home-bg {
  position: relative;
  background: url("../libs/home-office-gefbc799d0_1920.jpg") no-repeat;
  -webkit-background-size: cover;
  background-size: cover;
  opacity: 0.75;
  padding: 80px 0;
}
.greeting-wrapper {
  display: flex;
  justify-content: center;
  align-items: center;
  letter-spacing: 15px;
  line-height: 10.5em;
  span {
    display: block;
    font-family: cursive;
    font-size: 8em;
    color: #f3f1f5;
    transform: translate(0, -20%);
    transition: transform cubic-bezier(0.215, 0.61, 0.355, 1) 0.5s;
  }
}

.greeting-wrapper.-visible span {
  transform: translate(0, 0);
}
.greeting-wrapper span:nth-child(2) {
  transition-delay: 0.06s;
}
.greeting-wrapper span:nth-child(3) {
  transition-delay: 0.12s;
}
.greeting-wrapper span:nth-child(4) {
  transition-delay: 0.18s;
}
.greeting-wrapper span:nth-child(5) {
  transition-delay: 0.24s;
}
.greeting-wrapper span:nth-child(6) {
  transition-delay: 0.3s;
}
</style>
