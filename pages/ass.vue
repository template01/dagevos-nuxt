<template>
  <div>
    <dagevosHeader></dagevosHeader>
    <dagevosWat></dagevosWat>
    <dagevosFooter></dagevosFooter>

  </div>
</template>

<script>
import Logo from '~components/Logo.vue'
import dagevosHeader from '~components/dagevosHeader.vue'
import dagevosWat from '~components/dagevosWat.vue'
import dagevosFooter from '~components/dagevosFooter.vue'

export default {
  components: {
    Logo,
    dagevosHeader,
    dagevosWat,
    dagevosFooter
  }
}
</script>

<style>

</style>
