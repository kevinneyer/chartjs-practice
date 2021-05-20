<script>
import { Line } from 'vue-chartjs'

export default {
    name: 'line-chart',
    extends: Line,
    data() {
        return {
            chartdata: {
                labels: ["<3'", "4-5'", "6-10'", "11-15'", "16-20'", "21-30'", "31-50'" ],
                datasets: [
                    {
                    backgroundColor: '#54AE47',
                    data: [100, 75, 50, 100, 50, 25, 37],
                    tension: 0.0
                    }
                ]
                // yAxes: {
                //     labels: [
                //         '0%', '25%', '50%', '75%', '100%'
                //     ]
                // }
            },
            options: {
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
        }
    },
    mounted() {
        this.renderChart(this.chartdata, this.options)
    }
}
</script>