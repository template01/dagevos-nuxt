<template>
<div id="dagevosRene">

  <div class="container">

    <div class="row">
      <div class="col-sm-6">
        <div class="p-5" style="">
          <div class="">
            <h3 class="" v-html="reneProp.rene1.left.title"></h3>
          </div>
        </div>
      </div>
    </div>
    <div class="row">

      <div class="col-sm-6 ">
        <div class="" style="margin-left:-15px;margin-right:-15px;">
          <img style="width:100%;" class="" :src="reneProp.rene1.left.imgpath" alt="">
        </div>
      </div>
      <div class="col-sm-6 ">
        <div class="p-5" style="">
          <div class="" v-html="reneProp.rene1.right.content">
          </div>
        </div>
      </div>
    </div>
  </div>

  <div class="container">

    <div class="row">

      <div class="col-sm-6">
        <div class="p-5" style="">
          <div class="">
            <h4 class="mb-5" v-html="reneProp.rene2.left.title"></h4>
            <div class="" v-html="reneProp.rene2.left.content">
            </div>
          </div>
        </div>
      </div>
      <div class="col-sm-6">
        <div class="p-5" style="">
          <div class="">
            <h4 class="mb-5" v-html="reneProp.rene2.right.title"></h4>
            <div class="" v-html="reneProp.rene2.right.content">
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>

  <div class="container">

    <div class="row">

      <div class="col-sm-6 ">
        <div class="p-5" style="">
          <h4 class="mb-5" v-html="reneProp.rene3.left.title"></h4>

          <div class="" v-html="reneProp.rene3.left.content">
          </div>
        </div>
      </div>
      <div class="col-sm-6 ">
        <div class="" style="margin-left:-15px;margin-right:-15px;">
          <img style="width:100%" class="" :src="reneProp.rene3.right.imgpath" alt="">
        </div>
      </div>
    </div>
  </div>


</div>
</template>

<script>
export default {
  props: ['reneProp']
}
</script>

<style lang="scss">
#dagevosRene {
    a {
        text-decoration: none;
        color: inherit !important;
    }
}
</style>
