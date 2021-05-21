<script>
import { Line } from 'vue-chartjs'

export default {
    name: 'line-chart',
    extends: Line,
    props: ['chartData'],
    mounted() {
        this.renderChart(
            {
                labels: this.chartData.labels,
                datasets: [
                    {
                    data: this.chartData.data,
                    backgroundColor: '#54AE47',
                    tension: 0.0
                    }
                ]
            }, 
            {
                responsive: true, 
                maintainAspectRatio: false,
                layout: {
                    padding: 20
                },
                scales: {
                    yAxes: [{
                        ticks: {
                            min: 0,
                            stepSize: 25,

                            callback: function(value) {
                                return value + '%'
                            }
                        }
                    }]
                }
            }
        )
    }
}
</script>