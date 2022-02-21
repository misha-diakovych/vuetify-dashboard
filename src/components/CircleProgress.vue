<template>
  <v-row>
    <v-col class="text-center">
      <!--      <v-progress-circular-->
      <!--        :rotate="-90"-->
      <!--        :size="150"-->
      <!--        :width="20"-->
      <!--        :value="progressValue"-->
      <!--        color="teal"-->
      <!--      >-->
      <!--        {{ progressValue }}%-->
      <!--      </v-progress-circular>-->
      <radial-progress-bar
        :diameter="250"
        :completed-steps="progressValue"
        :total-steps="100"
        stop-color="#B3E5FC"
        start-color="#2E7D32"
        :stroke-width="20"
        :inner-stroke-width="20"
        inner-stroke-color="#706C6C30"
      >
        <span class="text-h4">{{ progressValue }}%</span>
      </radial-progress-bar>
      <div class="mt-5">
        <span class="grey--text">Completed appointments</span>
      </div>
    </v-col>
  </v-row>
</template>

<script>
import RadialProgressBar from "vue-radial-progress";
export default {
  name: "CircleProgress",
  components: {
    RadialProgressBar,
  },
  props: {
    progressValue: {
      type: Number,
      default: 0,
    },
  },
};
</script>

<style scoped>
::v-deep .v-progress-circular__overlay {
  stroke-linecap: round;
}
::v-deep .v-progress-circular__info {
  font-size: 2rem;
  color: black;
}
::v-deep .v-progress-circular__underlay {
  opacity: 0.5;
  color: rgba(208, 132, 132, 0.99);
}
</style>
