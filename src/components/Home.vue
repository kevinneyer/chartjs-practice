<template>
    <div>
        <h1>CHARTS</h1>
        <line-chart />
    </div>
</template>

<script>
import LineChart from './line-chart.vue'

export default {
    name: 'Home',
    components:{
        LineChart
    }
}
</script> 