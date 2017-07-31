<template>
<div>
  <dagevosHeader></dagevosHeader>
  <dagevosIndex :indexIndexProp="indexIndex" :indexRefsProp="indexRefs" :indexOpdrachtsProp="indexOpdrachts"></dagevosIndex>
  <dagevosFooter></dagevosFooter>

</div>
</template>

<script>
import Logo from '~components/Logo.vue'
import dagevosHeader from '~components/dagevosHeader.vue'
import dagevosIndex from '~components/dagevosIndex.vue'
import dagevosFooter from '~components/dagevosFooter.vue'

import axios from 'axios'


export default {
  components: {
    Logo,
    dagevosHeader,
    dagevosIndex,
    dagevosFooter
  },

  async asyncData({ query, error }) {
    let [indexIndexRes, indexRefsRes, indexOpdrachtsRes] = await Promise.all([
      axios.get('http://werkt.template01.info/json/index.json'),
      axios.get('http://werkt.template01.info/json/referenties.json'),
      axios.get('http://werkt.template01.info/json/opdrachtgevers.json'),
      // axios.get('https://jsonplaceholder.typicode.com/posts'),
      // axios.get('http://werkt.template01.info/json/referenties.json'),
    ])
    return {
       indexIndex: indexIndexRes.data,
       indexRefs: indexRefsRes.data,
       indexOpdrachts: indexOpdrachtsRes.data
    }
  }



}
</script>

<style>
.container {}

.title {
  font-family: "Quicksand", "Source Sans Pro", -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
  /* 1 */
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
