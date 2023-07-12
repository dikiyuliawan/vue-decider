<template>
  <div>
    <h1>Ask a question</h1>
    <div class="mb-3">
      <input
        type="text"
        name="question"
        id="question"
        class="form-control"
        v-model="question"
      />
    </div>

    <button
      class="btn animate__animated animate__fadeIn"
      v-if="question"
      @click="handleNext"
    >
      Next
    </button>

    <div class="error" v-if="error">your question is too short</div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      question: "",
      error: false,
    };
  },
  methods: {
    handleNext(e) {
      e.preventDefault();
      if (this.question.length <= 5) {
        this.error = true;
      } else {
        this.error = false;
        this.$emit("goto", 1);
        this.$emit("question", this.question);
      }
    },
  },
};
</script>
