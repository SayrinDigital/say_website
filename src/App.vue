<template>
<div id="app">
  <div class="uk-position-relative">
    <div class="uk-container say-container-medium">
      <nav id="mainnav" class="uk-navbar-container uk-navbar-transparent" uk-navbar>
        <div class="uk-navbar-left">

          <div class="uk-navbar-item uk-padding-remove">
            <a href="/">
              <img style="height: 40px;" src="./assets/logo.svg" class="uk-logo" uk-img="uk-img" alt="">
            </a>
          </div>

        </div>

        <div class="uk-navbar-right uk-hidden@m">

          <div class="uk-navbar-item">

            <a href="" class="uk-button style-b uk-button-text">
              <font-awesome-icon icon="bars" />
            </a>

          </div>

        </div>

        <div class="uk-navbar-right uk-visible@m">

          <ul class="uk-navbar-nav uk-visible@s">
            <li>
              <router-link to="/">Inicio</router-link>
            </li>
            <li>
              <router-link to="/team">Team</router-link>
            </li>
            <li><a href="https://desk.zoho.com/portal/sayrin/home">Soporte</a></li>
            <li><a target="_blank" href="https://accounts.zoho.com/signin?servicename=VirtualOffice&signupurl=https://workplace.zoho.com/orgsignup.do?signup.html">WorkPlace</a></li>
          </ul>

          <div class="uk-navbar-item">
            <div>

          <a class="uk-button style-a" href="mailto:hey@sayrin.cl">Contáctanos</a>

            </div>
          </div>


        </div>
      </nav>
    </div>
  </div>
  <div>
    <transition name="slide-left" mode="out-in">
      <div v-if="isShowing">
        <router-view />
      </div>
    </transition>
  </div>
    <Footer></Footer>
  <div id="page-router" v-bind:style="{backgroundColor: currentAccent }" ref="box"></div>
</div>
</template>

<script>
import UIkit from 'uikit';
import Icons from 'uikit/dist/js/uikit-icons';
import Footer from '@/components/Footer.vue'
import {
  TweenMax,
  Power4,
  TimelineLite
} from "gsap/TweenMax"




UIkit.use(Icons);
export default {
  name: 'app',
  components: {
    Footer
  },
  watch: {
    '$route'(to, from) {
      this.isShowing = false
      this.timeline.restart()
      this.randomiseBgColor()
    }
  },
  data() {
    return {
      timeline: null,
      isShowing: true,
      accents: ['#f4d222', "#FA5951", "#46b2f0"],
      currentAccent: '#f4d222'
    };
  },

  methods: {

    randomiseBgColor: function() {
      const logosToSample = this.accents.filter(color => color !== this.currentAccent)
      this.currentAccent = logosToSample[Math.floor(Math.random() * logosToSample.length)]
    }

  },

  mounted: function() {

    const {
      box
    } = this.$refs
    this.timeline = new TimelineLite({
      paused: true,
      onComplete: () => this.isShowing = true
    })

    this.timeline.fromTo(
      box,
      0.6, {
        scaleX: 0
      }, {
        scaleX: 1,
        transformOrigin: 'left',
        ease: Power4.easeInOut
      })
    this.timeline.to(box, 0.6, {
      scaleX: 0,
      transformOrigin: 'right',
      ease: Power4.easeInOut
    })



  }
};
</script>

<style lang="scss">
@import './assets/css/style.scss';

.slide-left-enter-active,
.slide-left-leave-active,
.slide-right-enter-active,
.slide-right-leave-active {
    transition-duration: 0.5s;
    transition-property: height, opacity, transform;
    transition-timing-function: cubic-bezier(0.55, 0, 0.1, 1);
    overflow: hidden;
}

.slide-left-enter,
.slide-right-leave-active {
    opacity: 0;
    transform: translate(2em, 0);
}

.slide-left-leave-active,
.slide-right-enter {
    opacity: 0;
    transform: translate(-2em, 0);
}
</style>
