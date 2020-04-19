<script>
import { Scatter } from 'vue-chartjs';

export default {
    extends: Scatter,
    props: {
        chartData: {
            type: Object,
            default: null
        },
        chartOption: {
            type: Object,
            default: null
        }
    },
    mounted () {
        this.renderChart(this.chartData, this.chartOption)
    },
}
</script>