<template>
  <div class="charts">
    <Row :gutter="16">
      <Col span="12">
        <VmChartBarLine title="Bar Chart" :xAxisData="dataBar1.xAxisData" :series="dataBar1.series">
        </VmChartBarLine>
      </Col>
      <Col span="12">
        <VmChartBarLine  title="Bar Chart" :xAxisData="dataBar2.xAxisData" :series="dataBar2.series">
        </VmChartBarLine>
      </Col>
    </Row>
    <Row :gutter="16">
      <Col span="12">
        <VmChartBarLine title="Line Chart" :xAxisData="dataLine1.xAxisData" :series="dataLine1.series">
        </VmChartBarLine>
      </Col>
      <Col span="12">
        <VmChartBarLine title="Line Chart" :xAxisData="dataLine2.xAxisData" :series="dataLine2.series">
        </VmChartBarLine>
      </Col>
    </Row>
    <Row :gutter="16">
      <Col span="12">
        <VmChartPie title="Pie Chart" :data="dataPie">
        </VmChartPie>
      </Col>
      <Col span="12">
        <VmChartRadar title="Radar Chart" :indicator="dataRadar.indicator" :data="dataRadar.data">
        </VmChartRadar>
      </Col>
    </Row>
  </div>
</template>

<script>
  import VmChartBarLine from '@/components/vm-chart-bar-line'
  import VmChartPie from '@/components/vm-chart-pie'
  import VmChartRadar from '@/components/vm-chart-radar'
  export default {
    name: 'Charts',
    components: {
      VmChartBarLine,
      VmChartPie,
      VmChartRadar
    },
    data: function () {
      return {
        dataBar1: {
          xAxisData: ['Shirt', 'Cardigan', 'Chiffon shirt', 'Pants', 'High heels', 'Sock'],
          series: [
            {
              name: 'Sales',
              type: 'bar',
              data: [50, 200, 360, 100, 100, 200]
            }
          ]
        },
        dataBar2: {
          xAxisData: ['Shirt', 'Cardigan', 'Chiffon shirt', 'Pants', 'High heels', 'Sock'],
          series: [
            {
              name: 'Sales',
              type: 'bar',
              data: [50, 200, 360, 100, 100, 200]
            },
            {
              name: 'Increment',
              type: 'bar',
              data: [5, 20, 36, 10, 10, 20]
            }
          ]
        },
        dataLine1: {
          xAxisData: ['Shirt', 'Cardigan', 'Chiffon shirt', 'Pants', 'High heels', 'Sock'],
          series: [
            {
              name: 'Sales',
              type: 'line',
              data: [50, 290, 360, 100, 100, 200]
            }
          ]
        },
        dataLine2: {
          color: ['#41b883', '#1d8ce0'],
          xAxisData: ['Shirt', 'Cardigan', 'Chiffon shirt', 'Pants', 'High heels', 'Sock'],
          series: [
            {
              name: 'Sales',
              type: 'line',
              data: [50, 130, 360, 100, 100, 200]
            },
            {
              name: 'Increment',
              type: 'line',
              data: [5, 50, 36, 10, 10, 20]
            }
          ]
        },
        dataPie: [
          {
            name: 'Java',
            value: 14
          },
          {
            name: 'C',
            value: 7
          },
          {
            name: 'C++',
            value: 6
          },
          {
            name: 'Python',
            value: 5
          },
          {
            name: 'C#',
            value: 4
          },
          {
            name: 'JavaScript',
            value: 3
          }
        ],
        dataRadar: {
          indicator: ['AQI', 'PM2.5', 'PM10', 'CO', 'NO2', 'SO2'],
          data: [
            {
              value: [4300, 10000, 28000, 35000, 50000, 19000],
              name: 'Budget allocation'
            },
            {
              value: [5000, 14000, 28000, 31000, 42000, 21000],
              name: 'Actual cost'
            }
          ]
        }
      }
    }
  }
</script>
