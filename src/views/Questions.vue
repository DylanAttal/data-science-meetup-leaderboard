<template>
  <div class="questions">
    <h1>This is the page where the questions go.</h1>
    <li v-for="question in questions" :key="question.qnumber">{{ question.title }}</li>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "questions",
  data: function() {
    return {
      questions: [
        {
          qnumber: 1,
          title: "Question 1",
          description: "How many unique cities are in the dataset?",
          format: "JSON",
          answer: 1965,
          base_score: 10
        },
        {
          qnumber: 2,
          title: "Question 2",
          description:
            "How many something goes here this is another question bro?",
          format: "JSON",
          answer: 1800,
          base_score: 10
        }
      ]
    };
  }
};
</script>

<style scoped>
</style>