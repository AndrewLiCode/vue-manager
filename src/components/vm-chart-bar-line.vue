<template>
  <div class="vm-chart-bar vm-panel">
    <div class="panel-body" :id="this.id" :style="{ height: height + 'px'}">
    </div>
  </div>
</template>
<script>
  import chartTheme from '@/theme/chartTheme.js'
  // import ECharts main module
  var echarts = require('echarts/lib/echarts')
  // import histogram
  require('echarts/lib/chart/bar')
  require('echarts/lib/chart/line')
  // import balloon and title components
  require('echarts/lib/component/tooltip')
  require('echarts/lib/component/title')
  require('echarts/lib/component/legend')

  export default {
    name: 'VmChartBarLine',
    props: {
      // Chart area height
      title: {
        type: String,
        default: 'Bar chart'
      },
      height: {
        type: Number,
        default: 400
      },
      // Chart shape color, ecahrt Select color rendering
      color: {
        type: Array,
        default: function () {
          return chartTheme.color
        }
      },
      // background color
      bgColor: {
        type: String,
        default: '#fff'
      },
      // Abscissa data
      xAxisData: {
        type: Array,
        required: true,
        default: function () {
          return ['Shirt', 'Cardigan', 'Bar chart', 'Pants', 'High heels', 'Sock']
        }
      },
      // Ordinate data
      series: {
        type: Array,
        required: true,
        default: function () {
          return [{
            name: 'Sales',
            type: 'bar',
            data: [5, 20, 36, 10, 10, 20]
          }]
        }
      }
    },
    data: function () {
      return {
        // Tick color
        axisColor: {
          type: String,
          default: '#797979'
        },
        // Divider line color
        splitLineColor: {
          type: String,
          default: '#dcdcdc'
        },
        chart: null
      }
    },
    computed: {
      // Generate a random id, Reuse chart components
      id: function () {
        return parseInt(Math.random() * 1000000)
      },
      legendData: function () {
        let legendData = []
        this.series.forEach(function (elem) {
          legendData.push(elem.name)
        })
        return legendData
      }
    },
    methods: {
      renderChart: function () {
        if (this.chart) {
          this.chart.dispose()
        }
        // initialize echart
        this.chart = echarts.init(document.getElementById(this.id))
        // customize eChart style
        this.chart.setOption({
          title: { text: this.title },
          legend: {
            icon: 'circle',
            data: this.legendData,
            bottom: 0
          },
          grid: {
            left: 30,
            right: 15
          },
          color: this.color,
          tooltip: {},
          xAxis: {
            data: this.xAxisData,
            axisLine: {
              lineStyle: {
                color: this.axisColor
              }
            }
          },
          yAxis: {
            axisLine: {
              lineStyle: {
                color: this.axisColor
              }
            },
            splitLine: {
              lineStyle: {
                color: '#dcdcdc'
              }
            }
          },
          series: this.series
        })
      }
    },
    watch: {
      xAxisData: function () {
        this.renderChart()
      },
      series: function () {
        this.renderChart()
      }
    },
    mounted: function () {
      this.renderChart()
    }
  }
</script>
