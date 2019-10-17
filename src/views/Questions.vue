<template>
  <div class="questions">
    <div class="wrapper">
      <li v-for="question in questions" :key="question.qnumber" class="card">
        <div class="card-head">{{ question.title }}</div>
        <div class="card-body">
          {{ question.description }}
          <br />
          <br />
          The expected answer type is {{ question.format }}.
        </div>
      </li>
    </div>
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
        .get(`http://ds-leaderboards.com:5000/api/questions`)
        .then(resp => (this.questions = resp.data));
    }
  }
};
</script>

<style scoped>
.card {
  width: 750px;
  border: 1px solid grey;
  border-radius: 4px;
  box-shadow: 5px 5px grey;
}

.card-head {
  border-bottom: 1px solid grey;
  background-color: #d0e4f5;
  font-size: 1.3rem;
}

.card-body {
  padding: 1rem;
}

.wrapper {
  margin-top: 2rem;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

li {
  list-style-type: none;
  margin-bottom: 2rem;
}
</style>