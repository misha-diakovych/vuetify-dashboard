<template>
  <v-card
    rounded="lg"
    elevation="0"
    outlined
    height="50px"
    class="d-flex align-center px-3"
  >
    <v-row>
      <v-col cols="2">
        <span>{{ card.title }}</span>
      </v-col>
      <v-col
        cols="2"
        offset="2"
        class="d-flex align-center justify-space-between"
      >
        <span class="mr-2 text-caption">
          {{ `${card.completedTasks}/${card.maxTasks}` }}
        </span>
        <v-progress-linear
          :value="card.progressValue"
          color="green"
          rounded
        ></v-progress-linear>
      </v-col>
      <v-col
        class="d-flex align-center justify-space-between"
        cols="3"
        offset="3"
      >
        <span class="light-green--text text--lighten-2 d-flex align-center">
          <v-icon class="mr-2" color="green">
            mdi-checkbox-marked-circle-outline
          </v-icon>
          Completed
        </span>
        <v-menu offset-y>
          <template v-slot:activator="{ on, attrs }">
            <v-icon
              class="blue-grey--text text--lighten-4"
              v-bind="attrs"
              v-on="on"
            >
              mdi-dots-horizontal
            </v-icon>
          </template>
          <v-list>
            <v-list-item>
              <v-list-item-title> Delete </v-list-item-title>
            </v-list-item>
          </v-list>
        </v-menu>
      </v-col>
    </v-row>
  </v-card>
</template>

<script>
export default {
  name: "TableCard",
  props: {
    card: {
      type: Object,
      required: true,
    },
  },
};
</script>

<style scoped></style>
