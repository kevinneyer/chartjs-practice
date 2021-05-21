<template>
    <div>
        <div>
            <line-chart 
            style="width: 100%; height: 100%"
            :chartData='chartData'
            />
        </div>
    </div>
</template>

<script>
import LineChart from './line-chart.vue'

export default {
    name: 'LineContainer',
    components:{
        LineChart
    },
    data() {
        return{
            chartData: {
                data: [100, 50, 30, 30, 12.5, 10, 10, 0],
                labels: ["<3'", "4-5'", "6-10'", "11-15'", "16-20'", "21-30'", "31-50'", "" ]
            }
        }
    }
}
</script>