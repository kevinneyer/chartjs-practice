<script>

import { Bar } from 'vue-chartjs'

export default {
    name: 'bar-chart',
    extends: Bar,
    props:['chartData'],
    data() {
        return {
             data: [5,5,5,5,5]
        }
    },
    methods: {
        findMaxBar() {
            let allData = this.data.concat(this.chartData.data)
            let max;
            for(let i = 0; i < allData.length; i++){
                max = allData[0]
                if( allData[i] > max){
                    max = allData[i]
                }
            }
            return max
        }
    },
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
                    data: this.data,
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
                        grid: {
                           display: false
                        },
                        ticks: {
                            min: 0,
                            stepSize: this.findMaxBar() / 2,
                            max: this.findMaxBar() + 2,
                            
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