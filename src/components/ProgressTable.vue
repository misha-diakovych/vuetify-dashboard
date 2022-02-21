<template>
  <v-row class="overflow-y-auto max-table-height mx-auto px-7">
    <v-col
      cols="12"
      class="pa-1 mx-auto"
      v-for="(card, index) in cardsArray"
      :key="index"
    >
      <table-card :card="card" />
    </v-col>
  </v-row>
</template>

<script>
import TableCard from "@/components/TableCard";
export default {
  name: "ProgressTable",
  components: { TableCard },
  data: () => ({
    cardsArray: [
      { title: "Test 1", completedTasks: 1, maxTasks: 1, progressValue: 56 },
      { title: "Test 2", completedTasks: 1, maxTasks: 1, progressValue: 56 },
      { title: "Test 3", completedTasks: 1, maxTasks: 1, progressValue: 56 },
      { title: "Test 4", completedTasks: 1, maxTasks: 1, progressValue: 56 },
      { title: "Test 5", completedTasks: 1, maxTasks: 1, progressValue: 56 },
      { title: "Test 6", completedTasks: 1, maxTasks: 1, progressValue: 56 },
      { title: "Test 7", completedTasks: 1, maxTasks: 1, progressValue: 56 },
      { title: "Test 8", completedTasks: 1, maxTasks: 1, progressValue: 56 },
      { title: "Test 9", completedTasks: 1, maxTasks: 1, progressValue: 56 },
      { title: "Test 10", completedTasks: 1, maxTasks: 1, progressValue: 56 },
      { title: "Test 11", completedTasks: 1, maxTasks: 1, progressValue: 56 },
    ],
  }),
};
</script>

<style scoped>
.max-table-height {
  max-height: calc(100% - 300px);
}
</style>
