<template>
  <div class="home">
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
      isIPhoneX: false
    };
  },
  created() {
    window.addEventListener("beforeunload", this.closing);
  },
  mounted() {
    this.isIPhoneX = isIPhoneX();
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
