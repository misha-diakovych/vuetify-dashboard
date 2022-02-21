<template>
  <v-row>
    <v-col cols="12">
      <v-sheet>
        <v-slide-group show-arrows>
          <v-slide-item
            class="ma-2"
            v-for="(card, index) in cardsArray"
            :key="`card-${index}`"
            v-slot="{ active, toggle }"
          >
            <slider-card :active="active" :toggle="toggle" :card="card" />
          </v-slide-item>
        </v-slide-group>
      </v-sheet>
    </v-col>
    <v-col cols="11" class="d-flex align-center justify-space-between mx-auto">
      <span class="grey--text">3 steps to complete</span>
      <v-menu offset-y :close-on-content-click="false">
        <template v-slot:activator="{ on, attrs }">
          <v-icon
            class="blue-grey--text text--lighten-4"
            v-bind="attrs"
            v-on="on"
          >
            mdi-calendar-range
          </v-icon>
        </template>
        <v-list class="pa-0">
          <v-list-item class="pa-0">
            <v-list-item-title>
              <v-date-picker
                v-model="picker"
                color="green lighten-1"
              ></v-date-picker>
            </v-list-item-title>
          </v-list-item>
        </v-list>
      </v-menu>
    </v-col>
  </v-row>
</template>

<script>
import SliderCard from "@/components/SliderCard";
export default {
  name: "ProgressSlider",
  components: { SliderCard },
  data: () => ({
    cardsArray: [
      { month: "January", progressValue: 10, completeTasks: 1, maxTasks: 0 },
      { month: "February", progressValue: 10, completeTasks: 1, maxTasks: 0 },
      { month: "March", progressValue: 10, completeTasks: 1, maxTasks: 0 },
      { month: "April", progressValue: 10, completeTasks: 1, maxTasks: 0 },
      { month: "May", progressValue: 10, completeTasks: 1, maxTasks: 0 },
      { month: "June", progressValue: 10, completeTasks: 1, maxTasks: 0 },
      { month: "July", progressValue: 10, completeTasks: 1, maxTasks: 0 },
      { month: "August", progressValue: 10, completeTasks: 1, maxTasks: 0 },
      { month: "September", progressValue: 10, completeTasks: 1, maxTasks: 0 },
      { month: "October", progressValue: 10, completeTasks: 1, maxTasks: 0 },
      { month: "November", progressValue: 10, completeTasks: 1, maxTasks: 0 },
      { month: "December", progressValue: 10, completeTasks: 1, maxTasks: 0 },
    ],
    picker: new Date(Date.now() - new Date().getTimezoneOffset() * 60000)
      .toISOString()
      .substr(0, 10),
  }),
};
</script>

<style scoped></style>
