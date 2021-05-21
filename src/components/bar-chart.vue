<script>

import { Bar } from 'vue-chartjs'

export default {
    name: 'bar-chart',
    extends: Bar,
    props:['chartData'],
    mounted() {
        this.renderChart(
            {
                labels: this.chartData.labels,
                datasets: [
                    {
                    label: 'You',
                    data: this.chartData.data,
                    backgroundColor: '#54AE47'
                    },
                    {
                    label: '0-2 Handicap',
                    data: [5,5,5,5,5],
                    backgroundColor: 'rgba(234, 138, 59, 1)'
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
                            stepSize: 2,
                            
                            callback: function(value) {
                                if (typeof(value) === 'number'){
                                    return " "
                                }
                            }
                        }
                    }]
                },
            }
            )
    }
}
</script>