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
            style="
              font-family: Courier New;
              font-size: 3em;
              color: #f3f1f5;
              text-shadow: 1.5px 1.5px #808080;
            "
            class="d-flex justify-center mt-5"
          >
            I am Emiri.
          </div>
          <div
            class="d-flex justify-center mt-3"
            style="
              font-family: Courier New;
              color: #f3f1f5;
              font-size: 1.25em;
              text-shadow: 1.5px 1.5px #808080;
            "
          >
            Frontend-developer
          </div>
        </div>
      </v-col>
    </v-row>
    <v-container>
      <v-row class="d-flex justify-center align-center mt-10 pt-10">
        <v-col
          cols="12"
          sm="8"
          v-for="card in cards"
          :key="card.Id"
          class="my-10"
        >
          <v-card
            hover
            style="height: 200px; width: 100%"
            @mouseover="onMouseOverCard(card.Id)"
            @mouseleave="onMouseLeaveCard(card.Id)"
            @click="goToLink(card.link)"
          >
            <div
              :class="`each-pages d-flex align-center  justify-center ${card.class}`"
            >
              <v-fade-transition>
                <div
                  v-if="card.isShow === true"
                  class="card-name"
                  style="font-family: cursive; font-size: 3.5em"
                >
                  {{ card.name }}
                </div>
              </v-fade-transition>
            </div>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
@Component({
  components: {},
})
export default class Home extends Vue {
  timeOut: number = 2000;
  cards: any[] = [
    // { Id: 1, name: "Home" ,src:"@/libs/woman-g8612c7b0e_640.jpg"},
    {
      Id: 1,
      name: "About Me",
      src: "/img/woman-g8612c7b0e_640.jpg",
      class: "about-me",
      isShow: false,
      link: "/aboutMe",
    },
    {
      Id: 2,
      name: "Skills",
      src: "/img/code-g182e5b0cb_640.jpg",
      class: "skills",
      isShow: false,
      link: "/skills",
    },
    {
      Id: 3,
      name: "Projects",
      src: "/img/phone-g44ec08d6e_640.jpg",
      class: "projects",
      isShow: false,
      link: "/projects",
    },
  ];

  created() {
    this.$nextTick(() => {
      this.setGreetingAnimation();

      setInterval(() => {
        this.setGreetingAnimation();
      }, this.timeOut * 2);
    });
  }

  setGreetingAnimation() {
    const CLASSNAME = "-up";
    const target = document.getElementsByClassName("greeting-wrapper")[0];
    target.classList.add(CLASSNAME);
    setTimeout(() => {
      target.classList.remove(CLASSNAME);
    }, this.timeOut);
  }

  onMouseOverCard(Id: number) {
    for (let c of this.cards) {
      if (c.Id === Id) {
        c.isShow = true;
        break;
      }
    }
  }

  onMouseLeaveCard(Id: number) {
    for (let c of this.cards) {
      if (c.Id === Id) {
        c.isShow = false;
        break;
      }
    }
  }

  goToLink(link: string) {
    this.$router.push(link);
  }
}
</script>

<style lang="scss">
//home title
.home-bg {
  position: relative;
  background: url("../libs/home-office-gefbc799d0_1920.jpg") no-repeat;
  -webkit-background-size: cover;
  background-size: cover;
  opacity: 0.7;
  padding: 150px 0;
}
.greeting-wrapper {
  display: flex;
  justify-content: center;
  align-items: center;
  letter-spacing: 10px;
  line-height: 10.5em;
  span {
    display: block;
    font-family: cursive;
    font-size: 8em;
    color: #f3f1f5;
    z-index: 2;
    transform: translate(0, -20%);
    transition: transform cubic-bezier(0.215, 0.61, 0.355, 1) 0.5s;
    text-shadow: 2px 2px #808080;
  }
}

//transition effect in Hello
.greeting-wrapper.-up span {
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

// each card items css
.each-pages {
  position: relative;
  cursor: pointer;
  opacity: 0.7;
  height: 100%;

  &:before {
    content: "";
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.3);
    transition: opacity 0.3s;
    opacity: 0;
    z-index: 2;
  }

  &:hover:before {
    opacity: 1;
  }

  .card-name {
    color: #f3f1f5;
    z-index: 2;
  }
}

.about-me {
  background: url("/img/woman-g8612c7b0e_640.jpg") no-repeat;
  -webkit-background-size: cover;
  background-size: cover;
  background-position: left top;
}

.skills {
  background: url("/img/code-g182e5b0cb_640.jpg") no-repeat;
  -webkit-background-size: cover;
  background-size: cover;
}

.projects {
  background: url("/img/phone-g44ec08d6e_640.jpg") no-repeat;
  -webkit-background-size: cover;
  background-size: cover;
}
</style>
