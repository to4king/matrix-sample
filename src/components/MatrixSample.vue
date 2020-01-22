<template>
  <div class="area" v-on:click.once="getPosition()">
    <Chart
      :chartData="this.chartData"
      :options="this.options"
    />
  </div>
</template>

<script>
import Chart from '../components/parts/Chart.vue';

const CHART_DATA = [];
const OPTIONS = [];

export default {
  name: 'MatrixSample',
  data: function() {
    return {
      chartData: CHART_DATA,
      OPTIONS : OPTIONS,
    };
  },
  components: {Chart},
  methods: {
    getPosition: function () {
      document.addEventListener('mousemove', function(e) {
        const _X = e.pageX;
        const _Y = e.pageY;
        alert(`X: ${_X}, Y: ${_Y}`);
      });
    },
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.area {
  min-height: 50em;
  min-width: 50em;
  background-color: #777733;
}
</style>
