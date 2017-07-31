<template>
<div>
  <div id="dagevosHeader">

    <b-navbar class="hidden-sm-down" toggleable type="inverse" variant="">

      <b-link class="navbar-brand" to="/">
        <span>
            <img src="~assets/svg/HetEchteWerk_CMYK.svg" />
          </span>
      </b-link>

      <b-collapse is-nav id="nav_collapse">
        <b-nav is-nav-bar class="ml-auto">
          <b-nav-item-dropdown text="<h4>Menu</h4>" class="" right>
            <h4><a class="ml-3 mr-3 mt-2 mb-2" href="/wat">Wat en voor wie is het?</a></h4>
            <h4><a class="ml-3 mr-3 mt-2 mb-2" href="/hoe">Hoe werkt het?</a></h4>
            <h4><a class="ml-3 mr-3 mt-2 mb-2" href="/referenties">Referenties</a></h4>
            <h4><a class="ml-3 mr-3 mt-2 mb-2" href="/rene">Rene Dagevos</a></h4>
            <h4><a class="ml-3 mr-3 mt-2 mb-0" href="/#contact">Contact</a></h4>
          </b-nav-item-dropdown>
        </b-nav>
      </b-collapse>
    </b-navbar>

    <b-navbar class="hidden-sm-up beigeBackground fixed-top " toggleable type="" id="" type="light">

      <b-nav-toggle class="mt-1" target="nav_collapse1"></b-nav-toggle>

      <b-link class="navbar-brand" to="/">
        <span><img class="brand-sm" src="~assets/svg/HetEchteWerk_CMYK_SM.svg"/></span>
      </b-link>

      <b-collapse is-nav id="nav_collapse1">
        <b-nav is-nav-bar class="ml-auto">
          <a class="nav-link" href="/wat">Wat en voor wie is het?</a>
          <a class="nav-link" href="/hoe">Hoe werkt het?</a>
          <a class="nav-link" href="/referenties">Referenties</a>
          <a class="nav-link" href="/rene">Rene Dagevos</a>
          <a class="nav-link" href="/#contact">Contact</a>

        </b-nav>
      </b-collapse>
    </b-navbar>
    <!-- CLONE FROM ABOVE TO ADD SPACING -->
    <b-navbar class="hidden-sm-up beigeBackground " toggleable type="" id="" type="light">
      <b-link class="navbar-brand" to="/">
        <span><img class="brand-sm" src="~assets/svg/HetEchteWerk_CMYK_SM.svg"/></span>
      </b-link>
    </b-navbar>

  </div>
  <transition name="slide">
    <b-navbar v-if="!hideNav" toggleable type="" id="dagevosHeaderFixed" class="fixed-top hidden-sm-down" type="light" style="background:#F6FBFF;">

      <b-nav-toggle class="mt-1" target="nav_collapse2"></b-nav-toggle>

      <b-link class="navbar-brand" to="/">
        <span><img src="~assets/svg/HetEchteWerk_CMYK_SM.svg"/></span>
      </b-link>

      <b-collapse is-nav id="nav_collapse2">
        <b-nav is-nav-bar class="ml-auto">
          <a class="nav-link" href="/wat">Wat en voor wie is het?</a>
          <a class="nav-link" href="/hoe">Hoe werkt het?</a>
          <a class="nav-link" href="/referenties">Referenties</a>
          <a class="nav-link" href="/rene">Rene Dagevos</a>
          <a class="nav-link" href="/#contact">Contact</a>

        </b-nav>
      </b-collapse>
    </b-navbar>
  </transition>

</div>
</template>
<script>
import _ from 'lodash'

export default {
  data() {
    return {
      hideNav: true
    }
  },
  methods: {
    test: function() {
      var vm = this
      var heightHeader = this.$el.offsetHeight + parseFloat(window.getComputedStyle(vm.$el).margin) * 2
      if (window.pageYOffset > heightHeader) {
        this.hideNav = false
      } else {
        this.hideNav = true

      }
    }
  },
  mounted() {
    this.test()
    if (_.VERSION) {
      console.log('underscore loaded')
    }
    // window.addEventListener('scroll', this.test)
    var vm = this
    window.addEventListener('scroll', _.throttle(() => {
      vm.test()
    }, 200))
  },

  created() {}

}
</script>

<style lang="scss">
@import "~assets/css/main.scss";

.slide-enter-active {
    transition: all 0.3s ease;
}
.slide-leave-active {
    transition: all 0.5s ease;
}
/* .slide-fade-leave-active below version 2.1.8 */
.slide-enter,
.slide-leave-to {
    transform: translateY(-200px);
    opacity: 0;
}

#dagevosHeader {

    font-family: 'Coolvetica Rg' !important;
    #logo {
        img {
            max-width: 100%;
        }
    }

    .dropdown-toggle::after {

        content: none;

    }

    .brand-sm {
        height: 40px;
        width: auto;
    }
    .dropdown {
        h4 {
            &:hover {
                -webkit-box-shadow: 0 2px 0 0 $purple;
                -moz-box-shadow: 0 2px 0 0 $purple;
                box-shadow: 0 2px 0 0 $purple;
            }
        }
    }

    .dropdown-menu {
        width: calc(25vw - 38px);
        border-color: white;

        h5 {
            font-family: 'Aileron' !important;
            box-sizing: border-box !important;

            a {
                box-sizing: border-box !important;
                display: inline-block;
                &:hover {}
            }
        }
    }

}

#dagevosHeaderFixed {}
</style>
