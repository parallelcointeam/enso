<template>
  <section class="flx frw fwr fsc">
    
<article v-for="(coin, slug) in bitnodes" :key="slug" class="flx pnl pnlbg fcl mar bitnode" amp-fx="fade-in">
  <button :on="'tap:AMP.navigateTo(url=\'//' + coin.slug + '.com-http.us/\')'" class="flx frw pnlhd">
    <figure><amp-img layout="fixed" :src="'https://i.com-http.us/' +coin.slug+  '/32'" width="32px" height="32px" :alt="coin.name"/></figure>
      <h3 class="flx fii fjc fai">
        <!-- <amp-fit-text height="32px" layout="flex-item" min-font-size="20px">{{coin.name}}🚀</amp-fit-text> -->
        {{coin.name}}🚀
        </h3>
  </button>
  <main class="flx fcl"><amp-live-list :id="coin.slug+ '-live'" data-poll-interval="15000" data-max-items-per-page="1" class="flx ">
  <button update on="tap:amp-live-list-update.update" class="btn btn-pri">You have updates</button>
      <div items class="flx fii"><div :id="coin.slug+ '-stat'" data-sort-time="1234567" data-update-time="20181021052854" class="flx">
     <Mining :slug="coin.slug" /> 
        </div></div>
      </amp-live-list></main>
<footer class="flx fcl">
  <ul class="sts">
      
<li><button :on="'tap:AMP.navigateTo(url=\'//' +  coin.slug + '.com-http.us/explorer\')'" class="blue">Explorer</button></li>
  <li><button :on="'tap:AMP.navigateTo(url=\'//' +  coin.slug + '.com-http.us/explorer\')'" class="light-blue">Info</button></li>
  </ul>
  </footer>
  </article>
  </section>
</template>



<script>
// import Mining from '@/components/amp/Mining.js'
import AmpTemplate from '@/components/amp/AmpTemplate.js'
import Mining from '@/components/amp/Mining.vue'

export default {
  components: {
    // Mining,
    AmpTemplate,
    Mining
  },
    props: {
    bitnodes:Array
  },
  head () {
    return {
      script: [
        { hid: "amp-fit-text", 'custom-element': "amp-fit-text", src: "https://cdn.ampproject.org/v0/amp-fit-text-0.1.js", async: '' },
         { hid: "amp-fx-collection", 'custom-element': "amp-fx-collection", src: "https://cdn.ampproject.org/v0/amp-fx-collection-0.1.js", async: '' },  
        { hid: "amp-iframe", 'custom-element': "amp-iframe", src: "https://cdn.ampproject.org/v0/amp-iframe-0.1.js", async: '' },
      ],
      link: [
        { rel: "preload", href: this.src, as: "image" },
      ]
    }
  }
}

</script>



<style>


</style>
