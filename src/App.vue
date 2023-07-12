<template>
  <div class="container">
    <transition name="fade" appear mode="out-in">
      <component
        :is="screens[position]"
        :question="question"
        @goto="handleGoto"
        @question="handleQuestion"
      />
    </transition>
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
.fade-enter-from {
  opacity: 0;
}
.fade-enter-active {
  transition: 0.5s;
}
.fade-enter-to {
  opacity: 1;
}

.fade-leave-from {
  opacity: 1;
}
.fade-leave-active {
  transition: 0.5s;
}
.fade-leave-to {
  opacity: 0;
}
</style>
