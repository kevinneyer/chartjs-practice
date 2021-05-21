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
                    label: 'You',
                    data: this.chartData.data,
                    backgroundColor: 'rgba(84, 174, 71, 0.8)',
                    tension: 0.0
                    },
                    {
                    label: '0-2 Handicap',
                    data: [95, 70, 45, 15, 25, 12.5, 5, 0],
                    backgroundColor: 'rgba(234, 138, 59, 0.5)',
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
                plugins: {
                    tooltip: {
                        enabled: false
                    }
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
                },
                elements: {
                    point:{
                        radius: 0
                    }
                }
            }
        )
    }
}
</script>