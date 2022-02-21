<template>
  <v-card
    rounded="lg"
    width="125px"
    height="75px"
    outlined
    :class="[active ? 'light-blue darken-4' : 'blue-grey lighten-5']"
    @click="toggle"
  >
    <v-card-text>
      <span
        class="font-weight-medium"
        :class="[active ? 'white--text' : 'light-blue--text text--darken-4']"
      >
        {{ card.month }}
      </span>
      <v-progress-linear
        value="15"
        color="green"
        background-color="white"
        rounded
      ></v-progress-linear>
      <span
        class="text-caption"
        :class="[active ? 'white--text' : 'grey--text']"
      >
        {{ `${card.completeTasks}/${card.maxTasks}` }}
      </span>
    </v-card-text>
  </v-card>
</template>

<script>
export default {
  name: "SliderCard",
  props: {
    card: {
      type: Object,
      required: true,
    },
    active: {
      type: Boolean,
      default: false,
    },
    toggle: {
      type: Function,
    },
  },
};
</script>

<style scoped></style>
