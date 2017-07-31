<template>
<div id="dagevosReferenties" class="container">

  <div class="container">

    <div class="row">
      <div class="col-sm-6">
        <div class="p-5" style="">
          <div class="">
            <h3 c class="pb-5" v-html="refsProp.referenties1.left.title">Hoe werkt Het echte Werkt?</h3>
            <div v-html="refsProp.referenties1.left.content">
            </div>
          </div>
        </div>

      </div>
      <div class="col-sm-6" style="margin-left:-15px;margin-right:-15px;">
        <img style="max-width:calc(100% + 45px)" class="" :src="refsProp.referenties1.right.imgpath" alt="">
      </div>
    </div>

  </div>

  <div class="container beigeBackground">
    <div class="row">

      <swiper class="beigeBackground" :options="swiperOption" ref="mySwiper" style="margin-left:-15px;margin-right:-15px;">
        <swiper-slide class="" v-for="referentie in refsProp.referenties">
          <div class="col-sm-6 float-left">
            <div class="p-5" style="">
              <div class="">
                <h6 class="" v-html="referentie.name"></h6>
                <h6 class="" v-html="referentie.function"></h6>
                <h1 v-html="referentie.blurb">
                </h1>
              </div>
            </div>
          </div>
          <div class="col-sm-6 float-left">
            <div class="p-5" style="">
              <div class="">
                <div v-html="referentie.content">
                </div>
              </div>
            </div>
          </div>
        </swiper-slide>
        <div class="swiper-pagination" slot="pagination"></div>
        <div class="swiper-button-prev" style='background-image:' slot="button-prev"></div>
        <div class="swiper-button-next" slot="button-next"></div>
        <!-- <div class="swiper-scrollbar" slot="scrollbar"></div> -->
      </swiper>


    </div>
  </div>
<!--
  <div class="container">

    <div class="row">
      <div class="col-sm-6">
        <div class="p-5" style="">
          <div class="">
            <h4 class="" v-html="opdrachtsProp.wie.title">Hoe werkt Het echte Werkt?</h4>
            <p v-html="opdrachtsProp.wie.blurb">
            </p>
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

  </div> -->

  <div class="container" style="">

    <div class="row blueBackground" style="margin-left:-30px;margin-right:-30px;">

      <div class="col-sm-2 p-4 flexer" v-for="opdrachtgever in opdrachtsProp.opdrachtgevers">
        <img style="max-width:100%;" class="flexerContentCenter" :src="opdrachtgever.imgpath" alt="">
      </div>

    </div>

  </div>



</div>
</template>
<script>
export default {
  props: ['refsProp', 'opdrachtsProp'],

  data() {
    return {
      swiperOption: {
        notNextTick: true,
        // autoplay: 3000,
        // grabCursor: true,
        setWrapperSize: true,
        autoHeight: true,
        pagination: '.swiper-pagination',
        paginationClickable: true,
        prevButton: '.swiper-button-prev',
        nextButton: '.swiper-button-next',
        // scrollbar: '.swiper-scrollbar',
        // mousewheelControl: true,
        observeParents: true,
        debugger: true,
        // swiper callbacks
        // swiper的各种回调函数也可以出现在这个对象中，和swiper官方一样
        onTransitionStart(swiper) {
          // console.log(swiper)
        },
      }
    }
  }
}
</script>

<style lang="scss">
#dagevosReferenties {
    a {
        text-decoration: none;
        color: inherit !important;
    }
}

.swiper-button-next {
    background-image: url("data:image/svg+xml;charset=utf-8,%3Csvg%20xmlns%3D'http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg'%20viewBox%3D'0%200%2027%2044'%3E%3Cpath%20d%3D'M27%2C22L27%2C22L5%2C44l-2.1-2.1L22.8%2C22L2.9%2C2.1L5%2C0L27%2C22L27%2C22z'%20fill%3D'%23552E87'%2F%3E%3C%2Fsvg%3E");
}

.swiper-button-prev {
    background-image: url("data:image/svg+xml;charset=utf-8,%3Csvg%20xmlns%3D'http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg'%20viewBox%3D'0%200%2027%2044'%3E%3Cpath%20d%3D'M0%2C22L22%2C0l2.1%2C2.1L4.2%2C22l19.9%2C19.9L22%2C44L0%2C22L0%2C22L0%2C22z'%20fill%3D'%23552E87'%2F%3E%3C%2Fsvg%3E");
}

.swiper-pagination-bullet-active {
    opacity: 1;
    background: #552E87;
}
</style>
