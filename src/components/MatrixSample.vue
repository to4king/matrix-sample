<template>
  <div v-on:click.once="getPosition()">
    <Chart
      class="area"
      :chartData="this.chartData"
      :chartOption="this.chartOption"
    />
  </div>
</template>

<script>
import Chart from '../components/parts/Chart.vue';

const dataBgColors = [
  '#f87979',
  '#77f777',
];
const CHART_DATA = {
  labels: ['January', 'Feburary'],
  datasets: [
    {
      label: '社員A',
      backgroundColor: dataBgColors[0],
      data: [
          {x:5, y:5},
          {x:-5, y:-5},
      ]
    },
    {
      label: '社員B',
      backgroundColor: dataBgColors[1],
      data: [
          {x:1, y:-3},
          {x:2, y:2},
      ]
    },
  ]
};
const CHART_OPTION = {
  responsive: true,
  scales: {
    yAxes: [{
      beginAtZero: false,
      ticks: {
        min: -5,
        max: 5,
        stepSize: 0.5
      }
    }],
    xAxes: [{
      beginAtZero: false,
      ticks: {
        min: -5,
        max: 5,
        stepSize: 0.5
      }
    }],
  },
  elements: {
    point: {
      radius: 6
    }
  },
  labels: ['好み', '得意']
}

export default {
  name: 'MatrixSample',
  data: function() {
    return {
      chartData: CHART_DATA,
      chartOption: CHART_OPTION,
    };
  },
  components: {Chart},
  methods: {
    getPosition: function () {
      document.addEventListener('mousemove', function(e) {
        const _X = e.pageX;
        const _Y = e.pageY;
        (`X: ${_X}, Y: ${_Y}`);
      });
    },
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.area {
  background-color: #eeeeee;
}
</style>
