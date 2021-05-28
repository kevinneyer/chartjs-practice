<script>
import { Line } from 'vue-chartjs';

export default {
    name: 'CurvyLineChart',
    extends: Line,
    mounted() {
            let chartElement = this.$refs.canvas;
            let context = chartElement.getContext("2d");
            let underLineGradient = context.createLinearGradient(0, 0, 0, 700);
            underLineGradient.addColorStop(0, "rgba(223, 255, 223, 1)");
            underLineGradient.addColorStop(.5, "rgba(223, 255, 223, 0)")
            underLineGradient.addColorStop(1, "transparent");

        this.renderChart( 
            {
            labels: ['','Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun', 'Jul', 'Aug', 'Sep', 'Oct', 'Nov', 'Dec'],
                datasets: [
                    { 
                        label: false,
                        data: [0,2,6,5.75,5,6,7,6,3.5,2,1.75,2,4],
                        backgroundColor: underLineGradient,
                        borderColor: '#008A00',
                        borderWidth: 2,
                        pointBackgroundColor: 'rgba(0, 138, 0, 1)',
                        pointRadius: 4

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
                                value = " "
                                return value
                            }
                        },
                    }],
                    xAxes: [{
                        grid: {
                            color: 'rgb(255, 0, 0)'
                        }
    
                    }]
                },
                elements: {
                    line: {
                        tension: .4
                    }
                },
                plugins: {
                    tooltip: {
                        callbacks: {
                            label: function() {
                                var label = context.dataset.label || '';

                                                        if (label) {
                            label += ': ';
                        }
                        if (context.parsed.y !== null) {
                            label += new Intl.NumberFormat('en-US', { style: 'currency', currency: 'USD' }).format(context.parsed.y);
                        }
                            }
                        }
                    }
                }
            }
        )
    }
}
</script>