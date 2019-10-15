<template>
  <div class="home">
    <Leaderboard />
  </div>
</template>

<script>
import Leaderboard from "@/components/Leaderboard.vue";

export default {
  name: "home",
  data: function() {
    return {};
  },
  components: {
    Leaderboard
  },
  methods: {}
};
</script>
