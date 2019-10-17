<template>
  <div>
    <h4 class="header">Data Science Leaderboard</h4>
    <div class="wrapper">
      <b-table
        id="leaderboard-table"
        :items="users"
        :fields="fields"
        :per-page="perPage"
        :current-page="currentPage"
        tbodyTrClass="row-class"
        small
      />
      <b-pagination
        v-model="currentPage"
        :total-rows="rows"
        :per-page="perPage"
        aria-controls="my-table"
      ></b-pagination>
      <p class="mt-1">Current Page: {{ currentPage }}</p>
    </div>
    <div class="footer">
      <p>
        This meetup sponsored by Suncoast Developers Guild
        <span>
          <a href="https://suncoast.io/" target="_blank">
            <img src="./assets/SDGLogo.png" id="sdg-logo" />
          </a>
        </span>and
        <span>
          <a href="https://www.ozk.com/labs/" target="_blank">
            <img src="./assets/BankOZKLogo.png" id="bank-ozk-logo" />
          </a>.
        </span>
      </p>
    </div>
  </div>
</template>

<script>
import axios from "axios";
import moment from "moment";

export default {
  name: "Leaderboard",
  data: function() {
    return {
      users: [],
      perPage: 10,
      currentPage: 1,
      fields: ["rank", "", "score", "username", "attempts", "last_submission"]
    };
  },
  created: function() {
    this.getUsers();
  },
  computed: {
    rows: function() {
      return this.users.length;
    }
  },
  methods: {
    getUsers: function() {
      return axios
        .get(`http://ds-leaderboards.com:5000/api/users`)
        .then(resp => (this.users = resp.data));
    },
    moment: function() {
      return moment();
    },
    rowClass: function() {
      return "row-class";
    }
  }
};
</script>

<style scoped>
#sdg-logo {
  height: 30px;
  cursor: pointer;
  margin-right: 4px;
}

#bank-ozk-logo {
  height: 90px;
  position: relative;
  bottom: 2px;
  cursor: pointer;
}

table /deep/ tr.row-class {
  font-size: 0.8rem !important;
}

.wrapper {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.header {
  width: 100%;
  margin: 0;
  padding: 20px;
  background-color: #d0e4f5;
  color: rgb(88, 88, 88);
  font-family: "Roboto", "Helvetica Neue", sans-serif;
}

.footer {
  width: 100%;
  margin: 0;
  padding: 20px;
  background-color: #d0e4f5;
  color: rgb(88, 88, 88);
  font-family: "Roboto", "Helvetica Neue", sans-serif;
  font-size: 1rem;
}
</style>
