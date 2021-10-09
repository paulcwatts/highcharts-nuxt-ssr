<template>
  <div>
    <!--
    When running "yarn generate", this works when you use the plugin method
    and global component.
    -->
    <client-only>
      <highcharts :options="chartOptions"/>
    </client-only>

    <client-only>
      <Chart :options="chartOptions" />
    </client-only>

  </div>
</template>
<script>
// When running "yarn generate", this import causes the error:
// ReferenceError: window is not defined
// You don't even need to actually use the component.
//import { Chart } from "highcharts-vue";

export default {
  components: {
    // This is a workaround: only import it in the client
    Chart: process.client ? require("highcharts-vue").Chart : {}
  },
  computed: {
    chartOptions: () => ({
      title: {
        text: "test",
      },
      series: [
        {
          type: "line",
          name: "test",
          data: [[1, 1], [2, 3]]
        },
      ],
    })
  }
}
</script>
