<template>
<div>

  <dagevosHeader></dagevosHeader>
  <dagevosReferenties :refsProp="refs" :opdrachtsProp="opdrachts"></dagevosReferenties>
  <dagevosFooter></dagevosFooter>

</div>
</template>

<script>
import Logo from '~components/Logo.vue'
import dagevosHeader from '~components/dagevosHeader.vue'
import dagevosReferenties from '~components/dagevosReferenties.vue'
import dagevosFooter from '~components/dagevosFooter.vue'
import axios from 'axios'
// import vueawesomeswiper from 'vue-awesome-swiper'


export default {
  components: {
    Logo,
    dagevosHeader,
    dagevosReferenties,
    dagevosFooter
  },

  async asyncData({
    query,
    error
  }) {
    let [refsRes, opdrachtsRes] = await Promise.all([
      axios.get('http://werkt.template01.info/json/referenties.json'),
      axios.get('http://werkt.template01.info/json/opdrachtgevers.json'),
      // axios.get('https://jsonplaceholder.typicode.com/posts'),
      // axios.get('http://werkt.template01.info/json/referenties.json'),
    ])
    return {
      refs: refsRes.data,
      opdrachts: opdrachtsRes.data
    }
  },



}
</script>

<style>

</style>
