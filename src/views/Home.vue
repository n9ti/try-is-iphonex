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
  mounted() {
    this.isIPhoneX = isIPhoneX();
  }
};
</script>
