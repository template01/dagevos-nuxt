<template>
<div id="dagevosWat">


  <div class="container">

    <div class="row">
      <div class="col-sm-6">
        <div class="p-5" style="">
          <div class="">
            <h3 class="pb-5" v-html="watProp.wat1.title">Hoe werkt Het echte Werkt?</h3>
            <div v-html="watProp.wat1.content">

            </div>
          </div>
        </div>

      </div>


      <div class="col-sm-6 beigeBackground">
        <div class="float-left" style="margin-left:-15px;margin-right:-15px;">
          <img style="max-width:100%;" class="" :src="watProp.wat2.imgpath" alt="">
        </div>

      </div>

    </div>
  </div>
  <!--
  <div class="index-full-cover heightTall" :style="{'background-image':'url('+watProp.wat2.imgpath+')'}">
  </div> -->

  <div class="container">
    <div class="row">
      <div class="col-sm-6">
        <div class="p-5">
          <div class="" v-html="watProp.wat3.left.content">
          </div>
        </div>
      </div>
      <div class="col-sm-6">
        <div class="p-5">
          <div class="" v-html="watProp.wat3.right.content">
          </div>
        </div>

      </div>
    </div>
  </div>
<hr class="m-5">

    <div class="container">

      <div class="row">
        <div class="col-sm-6">
          <div class="p-5" style="">
            <div class="">
              <h4 class="mb-5" v-html="opdrachtsProp.wie.left.title"></h4>
              <div v-html="opdrachtsProp.wie.left.content">
              </div>
            </div>
          </div>
        </div>
        <div class="col-sm-6">
          <div class="p-5" style="">
            <div class="">
              <div class="" v-html="opdrachtsProp.wie.right.content"></div>
            </div>
          </div>
        </div>
      </div>

    </div>

</div>
</template>

<script>
export default {
  props: ['watProp', 'opdrachtsProp']
}
</script>

<style lang="scss">
@import "~assets/css/main.scss";
h1,
h2,
h3,
h4,
h5,
h6 {
    color: $purple;
}

#dagevosWat {
    a {
        text-decoration: none;
        color: inherit !important;
    }
}
</style>
