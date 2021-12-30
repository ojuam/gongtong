<template>
 <div >
    <Ppt></Ppt>
    <Intro></Intro>
    <Divider></Divider>
    <Cardteam></Cardteam>
    <Divider1></Divider1>
    <Card1></Card1>
    <Card2></Card2>
    <Card3></Card3>
    
 </div>
</template>

<script>
import Ppt from '../components/ppt.vue'
import Divider from '../components/divider.vue'
import Intro from '../components/intro.vue'
import Divider1 from '../components/divider1.vue'
import Card3 from '../components/card3.vue'
import Cardteam from '../components/cardteam.vue'
import Card1 from '../components/card1.vue'

import Card2 from '../components/card2.vue'

export default {
 components:{
     Ppt,
    Divider,
    Intro,
    Divider1,
    Card3,
    Card1,
    Card2, 
    Cardteam
 }
}
</script>