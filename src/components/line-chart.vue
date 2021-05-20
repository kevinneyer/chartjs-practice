<script>
import { Line } from 'vue-chartjs'

export default {
    name: 'line-chart',
    extends: Line,
    mounted() {
        this.renderChart(
            {
                labels: ["<3'", "4-5'", "6-10'", "11-15'", "16-20'", "21-30'", "31-50'", "" ],
                datasets: [
                    {
                    backgroundColor: '#54AE47',
                    data: [100, 50, 30, 30, 12.5, 10, 10, 0],
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