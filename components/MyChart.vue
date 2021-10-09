<template>
  <div>
    <client-only>
      <highcharts :options="chartOptions"/>
    </client-only>
  </div>
</template>
<script>
export default {
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
