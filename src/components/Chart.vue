<template>
<div>
  <el-select v-model="value" placeholder="Select">
    <el-option
      v-for="item in options"
      :key="item.value"
      :label="item.label"
      :value="item.value">
    </el-option>
  </el-select>
  <LineChart v-if="value == 'line'">
  </LineChart>
    <BarChart v-else-if="value == 'bar'">
  </BarChart>
    <AreaChart v-else-if="value == 'area'">
  </AreaChart>
    <Donut v-else-if="value == 'donut'">
  </Donut>
    <HeatMap v-else-if="value == 'heatmap'">
  </HeatMap>
  </div>
</template>

<script>
import LineChart from './LineChart.vue'
import BarChart from './BarChart.vue'
import AreaChart from './AreaChart.vue'
import Donut from './Donut.vue'
import HeatMap from './HeatMap.vue'

export default {
  components:{
    LineChart,
    BarChart,
    AreaChart,
    Donut,
    HeatMap
  },
  data() {
    return {
      options: [{
        value: 'line',
        label: 'Line Chart'
      }, {
        value: 'bar',
        label: 'Stacked Bar'
      }, {
        value: 'donut',
        label: 'Donut/Pie'
      }, {
        value: 'area',
        label: 'Area Chart'
      }, {
        value: 'heatmap',
        label: 'Heat Map'
      }],
      value: ''
    }
    }
}
</script>
