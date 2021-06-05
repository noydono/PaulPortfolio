<template>
  <div id="app">
    <Navigation :scrollPosition="scrollPosition" class="navigation" />

    <transition v-on:before-leave="accueilLeave" v-on:css="false">
      <Accueil v-show="scrollPosition === 'accueil'" id="accueil" />
    </transition>

    <transition v-on:before-leave="proposLeave" v-on:css="false">
      <Propos v-show="scrollPosition === 'propos'" id="propos" />
    </transition>

    <transition v-on:before-leave="realisationLeave" v-on:css="false">
      <Realisation v-show="scrollPosition === 'realisation'" id="realisation" />
    </transition>

    <transition v-on:before-leave="contactLeave" v-on:css="false">
      <Contact v-show="scrollPosition === 'contact'" id="contact" />
    </transition>

    <transition name="footer">
      <Footer v-show="scrollPosition === 'contact'" id="footer" />
    </transition>
  </div>
</template>

<script>
import Navigation from "./components/navigation";
import Accueil from "./components/accueil";
import Propos from "./components/propos";
import Realisation from "./components/realisation";
import Contact from "./components/contact";
import Footer from "./components/footer";
export default {
  name: "App",
  components: {
    Navigation,
    Accueil,
    Propos,
    Realisation,
    Contact,
    Footer,
  },
  data() {
    return {
      scrollPosition: "accueil",
    };
  },
  mounted() {
    this.startListenEventWheel();
  },
  destroyed() {
    this.stopListenEventWheel();
  },
  methods: {
    handWheel(event) {
      const scrollY = event.deltaY;
      if (scrollY > 0 && this.scrollPosition === "accueil") {
        this.stopScrolling();
        this.scrollPosition = "propos";
      } else if (scrollY > 0 && this.scrollPosition === "propos") {
        this.stopScrolling();
        this.scrollPosition = "realisation";
      } else if (scrollY > 0 && this.scrollPosition === "realisation") {
        this.stopScrolling();
        this.scrollPosition = "contact";
      }

      if (scrollY < 0 && this.scrollPosition === "propos") {
        this.stopScrolling();
        this.scrollPosition = "accueil";
      } else if (scrollY < 0 && this.scrollPosition === "realisation") {
        this.stopScrolling();
        this.scrollPosition = "propos";
      } else if (scrollY < 0 && this.scrollPosition === "contact") {
        this.stopScrolling();
        this.scrollPosition = "realisation";
      }
    },
    stopScrolling() {
      this.stopListenEventWheel();
      setTimeout(this.startListenEventWheel, 1000);
    },
    startListenEventWheel() {
      document.addEventListener("wheel", this.handWheel);
    },
    stopListenEventWheel() {
      document.removeEventListener("wheel", this.handWheel);
    },

    accueilLeave(el) {
      el.style.animation = "accueil-out-in-propos 0.5s ease";
      document.querySelector("#propos").style.animation =
        "in-propos-out-accueil 0.5s ease";
    },

    proposLeave(el) {
      if (this.scrollPosition === "accueil") {
        el.style.animation = "propos-out-in-accueil 0.5s ease";
        document.querySelector("#accueil").style.animation =
          "in-accueil-out-propos 0.5s ease";
      } else if (this.scrollPosition === "realisation") {
        el.style.animation = "propos-out-in-realisation 0.5s ease";
        document.querySelector("#realisation").style.animation =
          "in-realisation-out-propos 0.5s ease";
      }
    },

    realisationLeave(el) {
      if (this.scrollPosition === "propos") {
        el.style.animation = "realisation-out-in-propos 0.5s ease";
        document.querySelector("#propos").style.animation =
          "in-propos-out-realisation 0.5s ease";
      } else if (this.scrollPosition === "contact") {
        el.style.animation = "realisation-out-in-contact 0.5s ease";
        document.querySelector("#contact").style.animation =
          "in-contact-out-realisation 0.5s ease";
      }
    },

    contactLeave(el) {
      if (this.scrollPosition === "realisation") {
        el.style.animation = "contact-out-in-realisation 0.5s ease";
        document.querySelector("#realisation").style.animation =
          "in-realisation-out-contact 0.5s ease";
      }
    },
  },
};
</script>

<style lang="sass">
/* Color Theme Swatches in RGBA */
$grayMarronDark: rgba(98,90,101, 1)
$graylight: rgba(219,227,229, 1)
$graydark: rgba(143,157,165, 1)
$marronlight: rgba(179,158,139, 1)
$marronDark: rgba(115,74,60, 1)

*
  box-sizing: border-box
  margin: 0
  padding: 0

html
  height: 100%
  width: 100%

body
  height: 100%
  width: 100%
  overflow: hidden

#app
  width: 100%
  height: 100%

#accueil
  position: absolute
  top: 0
  left: 0
  z-index: 0

#realisation
  position: absolute
  top: 0
  left: 0
  z-index: 10

#contact
  position: absolute
  top: 0
  left: 0
  z-index: 20

#footer
  position: absolute
  bottom: 0
  z-index: 21

.navigation
  z-index: 30
  position: fixed
  top: 45%
  left: 2%

@keyframes in-propos-out-accueil
  from
    transform: translateY(100%)
  to
    transform: translateY(0)

@keyframes propos-out-in-accueil
  from
    transform: translateY(0)
  to
    transform: translateY(100%)

@keyframes in-accueil-out-propos
  from
    transform: translateY(-100%)
  to
    transform: translateY(0)

@keyframes accueil-out-in-propos
  from
    transform: translateY(0)
  to
    transform: translateY(-100%)

@keyframes propos-out-in-realisation
  from
    transform: translateY(0)
  to
    transform: translateY(-100%)

@keyframes in-realisation-out-propos
  from
    transform: translateY(100%)
  to
    transform: translateY(0)

//real vers propos
@keyframes realisation-out-in-propos
  from
    transform: translateY(0)
  to
    transform: translateY(100%)

@keyframes in-propos-out-realisation
  from
    transform: translateY(-100%)
  to
    transform: translateY(0)

//target realisation
@keyframes realisation-out-in-contact
  from
    transform: translateY(0)
  to
    transform: translateY(-100%)
//target contact
@keyframes in-contact-out-realisation
  from
    transform: translateY(200vh)
  to
    transform: translateY(0)
//target contact
@keyframes contact-out-in-realisation
  from
    transform: translateY(0)
  to
    transform: translateY(200vh)
//target realisation
@keyframes in-realisation-out-contact
  from
    transform: translateY(-100%)
  to
    transform: translateY(0)


.footer-enter-active
    animation: footer-in 0.5s ease
.footer-leave-active
    animation: footer-in 0.5s ease reverse

@keyframes footer-in
  from
    transform: translateY(100%)
  to
    transform: translateY(0)
</style>
