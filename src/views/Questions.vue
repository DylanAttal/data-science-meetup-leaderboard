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
      return axios
        .get(`http://ds-leaderboards.com/api/questions`)
        .then(resp => (this.questions = resp.data));
    }
  }
};
</script>

<style scoped>
</style>