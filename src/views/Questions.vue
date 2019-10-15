<template>
  <div class="questions">
    <li v-for="question in questions" :key="question.qnumber">{{ question.description }}</li>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "questions",
  data: function() {
    return {
      questions: []
    };
  },
  created: function() {
    this.getQuestions();
  },
  methods: {
    getQuestions: function() {
      return (
        axios
          // TODO: hardcode the beginning of the url before /api to ds-leaderboard
          .get(`http://155.138.211.103/api/questions`)
          .then(resp => (this.questions = resp.data))
      );
    }
  }
};
</script>

<style scoped>
</style>