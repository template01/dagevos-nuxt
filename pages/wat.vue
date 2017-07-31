<template>
<div>
  <dagevosHeader></dagevosHeader>
  <dagevosWat :watProp="wat" :opdrachtsProp="opdrachts" ></dagevosWat>
  <dagevosFooter></dagevosFooter>

</div>
</template>

<script>
import Logo from '~components/Logo.vue'
import dagevosHeader from '~components/dagevosHeader.vue'
import dagevosWat from '~components/dagevosWat.vue'
import dagevosFooter from '~components/dagevosFooter.vue'

import axios from 'axios'

export default {
  components: {
    Logo,
    dagevosHeader,
    dagevosWat,
    dagevosFooter
  },

  async asyncData({
    query,
    error
  }) {
    let [watRes, opdrachtsRes] = await Promise.all([
      axios.get('http://werkt.template01.info/json/wat.json'),
      axios.get('http://werkt.template01.info/json/opdrachtgevers.json'),

    ])
    return {
      wat: watRes.data,
      opdrachts: opdrachtsRes.data,
    }
  }

}
</script>

<style>

</style>
