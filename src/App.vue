<template>
  <div class="container">
    <component :is="screens[position]" />
  </div>
</template>

<script>
import appInitial from "./components/appInitial.vue";
import appConfirm from "./components/appConfirm.vue";
import appResult from "./components/appResult.vue";

export default {
  components: {
    appInitial,
    appConfirm,
    appResult,
  },
  data() {
    return {
      screens: ["appInitial", "appConfirm", "appResult"],
      position: 0,
    };
  },
};
</script>

<style>
@import "./assets/style.css";
</style>
