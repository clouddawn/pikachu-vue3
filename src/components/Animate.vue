<template>
  <div class="animate">
    <div v-html="style" style="display: none"></div>
    <div class="pikachuHtml">
      <div class="skin">
        <div class="eye left"></div>
        <div class="eye right"></div>
        <div class="nose">
          <div class="oval"></div>
        </div>
        <div class="face left"></div>
        <div class="face right"></div>
        <div class="mouth">
          <div class="up">
            <div class="lip left"></div>
            <div class="lip right"></div>
          </div>
          <div class="down">
            <div class="tongue"></div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Animate",
  components: {},
  props: ["style"],
  data() {
    return {};
  },
  mounted() {

  },
  methods: {}
};
</script>

<style lang="scss" scoped>
.pikachuHtml {
  position: fixed;
  bottom: 0;
  left: 0;
  width: 100%;
  height: 50vh;
}
</style>