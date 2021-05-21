<template>
    <div>
        <h1>CHARTS</h1>
        <LineContainer />
        <BarContainer />
    </div>
</template>

<script>
import LineContainer from './LineContainer'
import BarContainer from './BarContainer'

export default {
    name: 'Home',
    components:{
        LineContainer,
        BarContainer
    }
}
</script> 