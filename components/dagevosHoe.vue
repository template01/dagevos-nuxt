<template>
<div id="dagevosHoe">

  <div class="container">

    <div class="row">
      <div class="col-sm-6">
        <div class="p-5" style="background-color: transparent; border-color: transparent;">
          <div class="">
            <h3 class="" v-html="hoeProp.hoe1.left.title">Hoe werkt Het echte Werkt?</h3>
          </div>
        </div>

      </div>
    </div>

    <div class="row">
      <div class="col-sm-6">

        <div class="float-left" style="margin-left:-15px;margin-right:-15px;">
          <img style="max-width:100%;" class="" :src="hoeProp.hoe1.left.imgpath" alt="">
        </div>
      </div>

      <div class="col-sm-6">
        <div class="p-5" style="background-color: transparent; border-color: transparent;">
          <div v-html="hoeProp.hoe1.right.content">
          </div>
        </div>
      </div>
    </div>
  </div>


  <div class="container">
    <div class="row">

      <div class="col-sm-6 beigeBackground">
        <div class="p-5" style="background-color: transparent; border-color: transparent;">
          <div v-html="hoeProp.hoe3.left.content">
          </div>
        </div>
      </div>
      <div class="col-sm-6 beigeBackground">
        <div class="p-5" style="background-color: transparent; border-color: transparent;">
          <div v-html="hoeProp.hoe3.right.content">
          </div>
        </div>
      </div>
    </div>
  </div>

  <div class="container">
    <div class="row">

      <div class="col-sm-6">
        <div class="p-5" style="background-color: transparent; border-color: transparent;">
          <h4 class="mb-5" v-html="hoeProp.hoe4.left.title"></h4>
          </p>
          <div v-html="hoeProp.hoe4.left.content">
          </div>
        </div>
      </div>
      <div class="col-sm-6">

        <div class="float-left" style="margin-left:-15px;margin-right:-15px;">
          <img style="max-width:100%;" class="" :src="hoeProp.hoe4.right.imgpath" alt="">
        </div>
      </div>
    </div>
  </div>


  <div class="container">
    <div class="row">

      <div class="col-sm-3 beigeBackground">

        <div class="hidden-sm-down" style="margin-left:-15px;margin-right:-15px;">
          <div class="index-full-cover" :style="{'background-image':'url('+hoeProp.hoe2.right.imgpath+')'}" style="position:absolute; right:0; top:0; height:100%; width:100%;">
          </div>
        </div>
        <div class="hidden-sm-up" style="margin-left:-15px;margin-right:-15px;">
          <div class="index-full-cover" :style="{'background-image':'url('+hoeProp.hoe2.right.imgpath+')'}" style="height:300px; width:100%;">
          </div>
        </div>
      </div>
      <div class="col-sm-9 blueBackground">
        <div class="p-5" style="background-color: transparent; border-color: transparent;">
          <h4 class="mb-5" v-html="hoeProp.tarieven.left.title"></h4>
          <div v-html="hoeProp.tarieven.left.content">
          </div>
        </div>
      </div>
    </div>
  </div>

</div>

</div>
</template>

<script>
export default {
  props: ['hoeProp']
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

#dagevosHoe {
    a {
        text-decoration: none;
        color: inherit !important;
    }
}
</style>
