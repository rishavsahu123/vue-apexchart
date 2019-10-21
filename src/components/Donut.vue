<template>
<div id="chart">
    <apexchart type=pie height=350 :options="chartOptions" :series="series" />
</div>    
</template>

<script>
import VueApexCharts from "vue-apexcharts";
export default{
    el:'#chart',
      components: {
        apexchart: VueApexCharts,
      },
      data() {
        return {
        series: [44, 55, 13, 43, 22],
        chartOptions: {
          labels: ['Team A', 'Team B', 'Team C', 'Team D', 'Team E'],
          responsive: [{
            breakpoint: 480,
            title: {
                text: 'Donut/Pie Chart',
                align: 'center'
            },
            options: {
              chart: {
                width: 200
              },
              legend: {
                position: 'bottom'
              }
            }
          }]
        }
      }
    }
      
    }
</script>>