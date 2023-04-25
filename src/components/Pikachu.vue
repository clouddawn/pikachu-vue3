<template>
  <div>
    <showCss :showMessage="showMessage" ref="showMessage"></showCss>
    <Animate :style="style"></Animate>
    <Options :currentTab="currentTab"
             :pause="pause"
             :play="play"
             :slowPlay="slowPlay"
             :normalPlay="normalPlay"
             :fastPlay="fastPlay"
             :playState="playState"></Options>
  </div>
</template>

<script>
import {style_css} from "../assets/style_css.js";
import {style_tag} from "../assets/style_css.js";

import showCss from "./showCss.vue";
import Animate from "./Animate.vue";
import Options from "./Options.vue";

export default {
  components: {
    showCss,
    Animate,
    Options
  },
  data() {
    return {
      showMessage: "",
      style: "",
      n: 0,
      intervalId: "",
      timeout: 100,
      playState: true,
      currentTab: ""
    };
  },
  mounted() {
    this.intervalId = setInterval(this.printMessage, this.timeout);
  },
  methods: {
    printMessage() {
      if (style_css[this.n]) {
        this.showMessage += style_css[this.n];
      }
      this.style += style_tag[this.n];
      this.n++;
      if (this.n === style_tag.length) {
        clearInterval(this.intervalId);
      }
      this.$refs.showMessage.ToBottom();
    },
    pause() {
      clearInterval(this.intervalId);
      this.playState = false;
      this.currentTab = "pause";
    },
    play() {
      this.intervalId = setInterval(this.printMessage, this.timeout);
      this.playState = true;
      this.currentTab = "play";
    },
    slowPlay() {
      this.timeout = 300;
      this.pause();
      this.play();
      this.currentTab = "slowPlay";
    },
    normalPlay() {
      this.timeout = 100;
      this.pause();
      this.play();
      this.currentTab = "normalPlay";
    },
    fastPlay() {
      this.timeout = 0;
      this.pause();
      this.play();
      this.currentTab = "fastPlay";
    }
  }
};
</script>

<style lang="scss" scoped>

</style>
