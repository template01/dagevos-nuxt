<template>
  <div>
    <dagevosHeader></dagevosHeader>
    <dagevosHoe :hoeProp="hoe"></dagevosHoe>
    <dagevosFooter></dagevosFooter>

  </div>
</template>

<script>
import Logo from '~components/Logo.vue'
import dagevosHeader from '~components/dagevosHeader.vue'
import dagevosHoe from '~components/dagevosHoe.vue'
import dagevosFooter from '~components/dagevosFooter.vue'
import axios from 'axios'

export default {
  components: {
    Logo,
    dagevosHeader,
    dagevosHoe,
    dagevosFooter
  },

  async asyncData({
    query,
    error
  }) {
    let [hoeRes] = await Promise.all([
      axios.get('http://werkt.template01.info/json/hoe.json'),

    ])
    return {
      hoe: hoeRes.data,
    }
  }

}
</script>

<style>

</style>
