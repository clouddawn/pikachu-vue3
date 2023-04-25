<template>
  <div class="showStyle" ref="showStyle">
    <pre>{{ showMessage }}</pre>
  </div>
</template>

<script>
export default {
  name: "showCss",
  components: {},
  props: ["showMessage"],
  data() {
    return {};
  },
  mounted() {

  },
  methods: {
    ToBottom() {
      this.$refs.showStyle.scrollTop = this.$refs.showStyle.scrollHeight;
    }
  }
};
</script>

<style lang="scss" scoped>
.showStyle {
  position: fixed;
  height: 50vh;
  top: 0;
  left: 0;
  width: 100%;
  padding: 10px;
  overflow-y: auto;
}

.showStyle::-webkit-scrollbar {
  display: none;
}
</style>