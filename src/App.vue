<template>
  <v-app>
    <v-main>
      <v-container>
        <h1>Your Progress</h1>
        <v-row>
          <v-col cols="3">
            <circle-progress :progress-value="68" />
          </v-col>
          <v-col cols="9">
            <progress-slider />
            <progress-table />
          </v-col>
        </v-row>
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
import CircleProgress from "@/components/CircleProgress";
import ProgressSlider from "@/components/ProgressSlider";
import ProgressTable from "@/components/ProgressTable";

export default {
  name: "App",

  components: {
    ProgressTable,
    ProgressSlider,
    CircleProgress,
  },

  data: () => ({
    //
  }),
};
</script>
