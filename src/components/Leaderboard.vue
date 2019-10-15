<template>
  <div>
    <h1 class="header">Data Science Leaderboard</h1>
    <table class="paleBlueRows">
      <tr>
        <th>Rank</th>
        <th>Team</th>
        <th>Score</th>
        <th>Last Submission</th>
      </tr>
      <tr>
        <td>1</td>
        <td>The Tigers</td>
        <td>35</td>
        <td>8:00pm</td>
      </tr>
    </table>
  </div>
</template>

<script>
export default {
  name: "Leaderboard"
};
</script>

<style scoped>
.header {
  width: 100%;
  margin: 0;
  padding: 30px;
  background-color: #3f51b5;
  color: #fff;
  font-family: "Roboto", "Helvetica Neue", sans-serif;
}

table.paleBlueRows {
  font-family: "Times New Roman", Times, serif;
  border: 1px solid #ffffff;
  width: 100%;
  text-align: center;
  border-collapse: collapse;
}

table.paleBlueRows td,
table.paleBlueRows th {
  border: 1px solid #ffffff;
  padding: 3px 2px;
}

table.paleBlueRows tbody td {
  font-size: 13px;
}

table.paleBlueRows tr:nth-child(even) {
  background: #d0e4f5;
}

table.paleBlueRows thead {
  background: #0b6fa4;
  border-bottom: 5px solid #ffffff;
}

table.paleBlueRows thead th {
  font-size: 17px;
  font-weight: bold;
  color: #ffffff;
  text-align: center;
  border-left: 2px solid #ffffff;
}

table.paleBlueRows thead th:first-child {
  border-left: none;
}

table.paleBlueRows tfoot {
  font-size: 14px;
  font-weight: bold;
  color: #333333;
  background: #d0e4f5;
  border-top: 3px solid #444444;
}

table.paleBlueRows tfoot td {
  font-size: 14px;
}
</style>
