<template>
    <div>
        <h1>CHARTS</h1>
        <div>
            <line-chart 
            style="width: 100%; height: 100%"
/>
        </div>
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