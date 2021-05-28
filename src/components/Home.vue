<template>
    <div>
        <h1>CHARTS</h1>
        <LineContainer />
        <BarContainer />
            <CurvylineChart />
    </div>
</template>

<script>
import LineContainer from './LineContainer'
import BarContainer from './BarContainer'
import CurvylineChart from './curvyline-chart.vue'


export default {
    name: 'Home',
    components:{
        LineContainer,
        BarContainer,
        CurvylineChart
    }
}
</script> 

<style>
    .curvy-div{
        height: 50px
    }
</style>