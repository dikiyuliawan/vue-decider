<template>
  <div class="container">
    <component
      :is="screens[position]"
      @goto="handleGoto"
      @question="handleQuestion"
    />
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
      question: "",
    };
  },
  methods: {
    handleGoto(position) {
      this.position = position;
    },
    handleQuestion(question) {
      this.question = question;
    },
  },
};
</script>

<style>
@import "./assets/style.css";
</style>
