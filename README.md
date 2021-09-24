<div align=center>
  <p>
    <strong>Vue Panel Framework,</strong>
  </p>
</div>
</div>
<br>
<div align=center>
  <img src="https://img.shields.io/badge/Dependency-Vue2.3.3-yellow.svg?style=flat">
  <img src="https://img.shields.io/badge/Dependency-iView2.0-blue.svg?style=flat">
  <img src="https://img.shields.io/badge/Dependency-ECharts3.6.2-red.svg?style=flat">
  <img src="https://img.shields.io/badge/License-MIT-blue.svg?style=flat">
</div>

<br>

## Installation

1. install node / npm(cnpm)
2. npm install
3. npm run dev
4. visit localhost:8080

## Dependencies

1. Vue2.0
2. iView
3. ECharts

## Global Style

> You can customize the global style by modifying the less file theme / index.less

## Component use

### example

#### vm-progress

| Attributes | description                | Type    | default        |
| ---------- | -------------------------- | ------- | -------------- |
| title      | Custom title               | String  | Progress       |
| data       | Structured data displayed  | Array   | See Properties |

**Attributes**

```
    props: {
      title: {
        type: String,
        default: 'Progress'
      },
      data: {
        type: Array,
        default: function () {
          return [
            {
              name: 'Andrew Li',
              tags: ['hansome', 'cool'],
              value: 100
            }
          ]
        }
      }
    }
```

**Application**

```
<VmProgress title="work progress" :data="dataProgress"></VmProgress>
...
export default {
  data: function () {
   return dataProgress: [
      {
        name: 'Andrew Li',
        tags: ['Very handsome', 'A funny guy'],
        value: 90
      },
      {
        name: 'Marta Gomes',
        tags: ['beautiful', 'Perceptual', 'Literature and art'],
        value: 30
      },
      {
        name: 'Michael Carmon',
        tags: ['temperament', 'Terrific'],
        value: 80
      },
      {
        name: 'Melissa Rose',
        tags: ['Talented girl', 'Work hard', 'learned'],
        value: 20
      },
      {
        name: 'Tony Zolla',
        tags: ['Very handsome', 'Great'],
        value: 100
      }
    ],
  }
}

```

### vm-timeline

| Attributes | description                | Type    | default        |
| ---------- | -------------------------- | ------- | -------------- |
| title      | Custom title               | String  | Timeline       |
| data       | Structured data displayed  | Array   | See Properties |

**Attributes**

```
   props: {
      title: {
        type: String,
        default: 'Timeline'
      },
      data: {
        type: Array,
        default: function () {
          return [
            {
              date: '6/26/2017',
              time: '11:58 am',
              content: 'Carry out VmManager timeline component'
            }
          ]
        }
      }
    }
```

**Application**

```
<VmTimeline :data="dataTimeline"></VmTimeline>
...

export default {
  data: function () {
    return {
      dataTimeline: [
        {
          date: '7/15/2017',
          time: '8:35 am',
          content: 'Lorem ipsum dolor sit amet consiquest dio'
        },
        {
          date: '7/15/2017',
          time: '8:35 am',
          content: 'Lorem ipsum dolor sit amet consiquest dio'
        },
        {
          date: '7/15/2017',
          time: '8:35 am',
          content: 'Lorem ipsum dolor sit amet consiquest dio'
        },
        {
          date: '7/15/2017',
          time: '8:35 am',
          content: 'Lorem ipsum dolor sit amet consiquest dio'
        },
        {
          date: '7/15/2017',
          time: '8:35 am',
          content: 'Lorem ipsum dolor sit amet consiquest dio'
        }
      ]
    }
  }
}
```

### vm-chart-bar-line

| Attributes | description                                              | Type    | default        |
| ---------- | -------------------------------------------------------- | ------- | -------------- |
| title      | Custom title                                             | String  | Timeline       |
| height     | Chart height                                             | Number  | 400            |
| color      | Chart rendering color, Extract from color array in order | Array   | See Properties |
| bgColor    | Chart background color                                   | String  | #fff           |
| xAxisData  | Abscissa value                                           | Array   | See Properties |
| series     | Ordinate value                                           | Array   | See Properties |

**Attributes**

```
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
          return ['Shirt', 'Cardigan', '雪纺衫', '裤子', '高跟鞋', '袜子']
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
    }
```

**Application**

```
<VmChartBarLine  title="Two-dimensional bar chart" :xAxisData="dataBar2.xAxisData" :series="dataBar2.series">
</VmChartBarLine>
...

export default {
  data: function () {
    return {
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
    }
  }
}
```

### vm-table

| Attributes | description                                        | Type    | Default     |
| ---------- | -------------------------------------------------- | ------- | ----------- |
| title      | Custom title                                       | String  | Basic Table |
| type       | Editable and non-editable,Non-editable value edit  | String  | null        |
| columns    | Table column configuration description             | Array   | []          |
| data       | Structured data displayed                          | Array   | []          |

**Attributes**

```
   props: {
      title: {
        type: String,
        default: 'Basic Table'
      },
      type: String,
      columns: Array,
      data: Array
    }
```

**Event** Available in edit mode

| Event name | description                          | return value             |
| ---------- | ------------------------------------ | ------------------------ |
| edit-ok    | Triggered after editing              | Edit the form's data     |
| add-ok     | Triggered after adding               | Add form data            |
| delete-ok  | Triggered after deletion is complete | Deleted data collection  |

**Application**

```
<VmTable title="Editable form"
         type="edit"
         :columns="dataColumns"
         :data="dataTable"
         v-on:add-ok="add"
         v-on:edit-ok="edit"
         v-on:delete-ok="deletefn">
</VmTable>
...

export default {
  methods: {
    add: function (data) {
      //...
    },
    edit: function (data) {
      //...
    },
    deletefn: function (data) {
      //...
    }
  },
  data: function () {
    return {
      dataColumns: [
        {
          title: 'No',
          key: 'id'
        },
        {
          title: 'Name',
          key: 'name'
        },
        {
          title: 'Age',
          key: 'age'
        },
        {
          title: 'Address',
          key: 'address'
        }
      ],
      dataTable: [
        {
          id: '65416843154',
          name: 'David',
          age: 18,
          address: '4807 Fairway Drive, Fairfield, CA'
        },
        {
          id: '65416843654',
          name: 'Rob',
          age: 25,
          address: '4108 Hayhurst Lane, West Bloomfield, MI'
        },

        ...

        {
          id: '65416843194',
          name: 'Kevin',
          age: 30,
          address: '3826 Cambridge Court, Gilbert, AZ'
        },
      ]
    }
  }
}
```
