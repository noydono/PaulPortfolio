<template>
  <v-app>
    <Navbar />

    <v-main>
      <v-parallax rel="preload" src="./assets/image/fern-1250903_1920.jpg"></v-parallax>
      <Accueil />
      <v-parallax rel="preload" src="./assets/image/mitchell-luo-_NzW-__ohkM-unsplash.jpg"></v-parallax>
      <Realisation />
      <v-parallax rel="preload" src="./assets/image/joshua-bartell-6vvIBTvL90A-unsplash.jpg">
        <v-container
          id="contact"
          class="container d-flex flex(row justify-center align-center"
        >
          <v-row>
            <v-col
              class="d-flex flex-column justify-center align-center contact"
            >
              <h2 class="mt-5 mb-2">Contact</h2>
              <v-row>
                <i class="far fa-envelope mr-2" style="font-size: 30px"></i>
                <p>Pauldubois92@laposte.net</p>
              </v-row>
            </v-col>
          </v-row>
        </v-container>
      </v-parallax>
      <Contact />
    </v-main>
  </v-app>
</template>

<script>
import Navbar from "./components/navbar";
import Accueil from "./components/accueil";
import Realisation from "./components/realisation";
import Contact from "./components/contact";
export default {
  name: "App",

  components: {
    Navbar,
    Accueil,
    Realisation,
    Contact,
  },

  data: () => ({
    //
  }),
};
</script>

<style lang="sass" >
@import url('https://fonts.googleapis.com/css2?family=Open+Sans+Condensed:ital,wght@0,300;0,700;1,300&display=swap')
*
  font-family: 'Open Sans Condensed', sans-serif
  box-sizing: border-box
  margin: 0
  padding: 0

.contact
  & p
    font-size: 1.25rem
    text-align: center
    width: 40%
    color: #DFCC93
  & h2
    color: #DFCC93
    font-size: 2rem
  & i
    color: #DFCC93
</style>


