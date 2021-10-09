<template>
  <div>
    <client-only>
      <Chart/>
    </client-only>
  </div>
</template>
<script>
import { Chart } from "highcharts-vue";

export default {
  components: { Chart }
};
</script>
