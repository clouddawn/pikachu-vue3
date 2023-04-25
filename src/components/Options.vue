<template>
  <div>
    <div id="buttons">
      <button class="select"
              id="btnPause"
              @click="pause"
              :class="{selected:currentTab === 'pause' || currentTab === 'play'}"
              v-if="playState === true">暂停
      </button>
      <button class="select"
              id="btnPlay"
              @click="play"
              :class="{selected:currentTab === 'pause' || currentTab === 'play'}"
              v-if="playState === false">播放
      </button>
      <button class="select"
              id="btnSlow"
              @click="slowPlay"
              :class="{selected:currentTab === 'slowPlay'}">慢速
      </button>
      <button class="select"
              id="btnNormal"
              @click="normalPlay"
              :class="{selected:currentTab === 'normalPlay'}">中速
      </button>
      <button class="select"
              id="btnFast"
              @click="fastPlay"
              :class="{selected:currentTab === 'fastPlay'}">快速
      </button>
    </div>
  </div>
</template>

<script>
export default {
  name: "Options",
  components: {},
  props: ["currentTab", "playState", "pause", "play", "slowPlay", "normalPlay", "fastPlay"],
  data() {
    return {};
  },
  mounted() {

  },
  methods: {}
};
</script>

<style lang="scss" scoped>
#buttons {
  position: fixed;
  right: 0;
  top: 0;
  z-index: 10;
  display: flex;
  flex-direction: column;
  margin-top: 15px;
  margin-right: 10px;
}

#buttons > button {
  margin-bottom: 10px;
  padding: 4px 8px;
}

.selected {
  background-color: #f60;
  color: white;
  border-color: #ff6600;
}
</style>