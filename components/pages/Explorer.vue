<template>
  <section class="flx fcl fii">
<Panel class="flx fii">
  <Blocks  :slug="slug" :symbol="symbol" :name="name" :algo="algo"  :lastblock="lastblock" /></Panel>

    
  </section>
</template>


<script>
import Panel from '~/components/elements/Panel.vue'

import Blocks from '~/components/amp/Blocks.vue'


export default {
  components: {
    Panel,
    Blocks,
  },
    props: {
    slug:String,
    name:String,
    symbol:String,
    algo:String,
    lastblock:Number,
  }
}
</script>

<style>




</style>
