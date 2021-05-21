<template>
    <div>
        Bar Container
        <bar-chart 
        :chartData='chartData'/>
    </div>
</template>

<script>
import BarChart from './bar-chart.vue'

export default {
    name: 'BarContainer',
    components: {
        BarChart
    },
    data() {
        return { 
            chartData: {
                labels: ['Good Lie', 'Bad Lie', 'No Shot', 'Penalty', 'OB/Lost'],
                data: [3.1, 3.1, 3.1, 3.1, 3.1]
            }
        }
 
    }
}
</script>