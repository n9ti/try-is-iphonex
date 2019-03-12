<template>
  <div class="home">
    <h1>{{ screenHeight }}</h1>
    <img v-if="isIPhoneX" alt="iPhone X" src="/img/iphonex.png">
    <img v-else alt="Not iPhone X" src="/img/not-iphonex.png">
  </div>
</template>

<script>
import isIPhoneX from "is-iphonex";

export default {
  name: "home",
  data() {
    return {
      isIPhoneX: false,
      screenHeight: 0
    };
  },
  created() {
    window.addEventListener("beforeunload", this.closing);
  },
  mounted() {
    this.isIPhoneX = isIPhoneX();
    this.screenHeight = window.screen.height;
  },
  methods: {
    closing(e) {
      e.preventDefault();
      e.returnValue = "";
      return false;
    }
  }
};
</script>
