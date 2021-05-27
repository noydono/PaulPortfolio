<template>
  <v-container id="realisation"  fluid class="container">
    <v-row>
      <v-col class="d-flex flex-column justify-center align-center">
        <h2 class="mt-5">Réalisation</h2>
        <p class="mt-5 mb-15">
          Voici ci-dessous mes quelques réalisations que j’ai pu effectuer
          pendant ma formation.
        </p>
      </v-col>
    </v-row>
    <v-row class="mb-5">
      <v-col class="d-flex flex-row justify-center align-center mx-15">
        <masonry :cols="3" :gutter="{ default: '30px', 700: '50px' }">
          <div
            class="realisation-container"
            :class="`realisation-container-${item.position}`"
            v-for="(item, index) in posts"
            :key="index"
            @mouseenter="hover = item.position"
            @mouseleave="hover = ''"
          >
            <img width="100%" :src="item.src" />
            <transition name="hover">
              <div v-if="hover === item.position" class="realisation-container-hover d-flex flex-column justify-center align-center">
                  <h3>{{item.title}}</h3>
                  <p>{{item.content}}</p>
              </div>
            </transition>
          </div>
        </masonry>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: "realisation",

  data() {
    return {
      hover: "",
      posts: [
        {
          position: 1,
          title: "Logo Kindred",
          src: require("../assets/image/1.jpg"),
          lazySrc:require("../assets/image/thumbnails/1_tn.jpg"),
          content:
            "Plaquette de bois meurisier, découpé et recouvert d’epoxy verte et incolore.",
        },
        {
          position: 2,
          title: "Marqueterie Hollow Knight",
          src: require("../assets/image/2.jpg"),
          lazySrc:require("../assets/image/thumbnails/2_tn.jpg"),
          content:
            "Marqueterie effectuée avec le procéder de Boule. Dessin inspiré de jeu vidéo.",
        },
        {
          position: 3,
          title: "Marqueterie Momonoké",
          src: require("../assets/image/3.jpg"),
          lazySrc:require("../assets/image/thumbnails/3_tn.jpg"),
          content:
            "Marqueterie inspirée de Film japonais. Essence du plaquage,noyer noir,meurisier,acajou.",
        },
        {
          position: 4,
          title: "Projet de fin de formation",
          src: require("../assets/image/4.jpg"),
          lazySrc:require("../assets/image/thumbnails/4_tn.jpg"),
          content:
            "Meuble de style asiatqiue, pieds inspirés des arches Torii Japonaise. Portes usinés à la CNC,gardant des gravures representant des nuages.",
        },
        {
          position: 5,
          title: "Meuble de cuisine",
          src: require("../assets/image/5.jpg"),
          lazySrc:require("../assets/image/thumbnails/5_tn.jpg"),
          content:
            "Meuble en particule stratifié noir mat. Comptoir en stratifié Bambou.",
        },
        {
          position: 6,
          title: "Armoire à Pharmacie",
          src: require("../assets/image/6.jpg"),
          lazySrc:require("../assets/image/thumbnails/6_tn.jpg"),
          content:
            "Premier meuble effectué, avec des outils manuels seulement. Sculpture de Totoro en tête du meuble.",
        },
        {
          position: 7,
          title: "Modern 2.0",
          src: require("../assets/image/7.jpg"),
          lazySrc:require("../assets/image/thumbnails/7_tn.jpg"),
          content:
            "Meuble retro effectuer en mélamine paqué meurisier, avec des alaises en  meurisier massif. Pattes en massif meurisier.",
        },
        {
          position: 8,
          title: "Meuble commercial",
          src: require("../assets/image/8.jpg"),
          lazySrc:require("../assets/image/thumbnails/8_tn.jpg"),
          content:
            "Mon plus gros meuble réalisé à date. En contreplaqué russe, plaquer en stratifié blanc et gris mat. Effectué pour d’autres filières du CFP.",
        },
        {
          position: 9,
          title: "Table à pattes galbées",
          src: require("../assets/image/9.jpg"),
          lazySrc:require("../assets/image/thumbnails/9_tn.jpg"),
          content:
            "Table effectuée en bois massif meurisier. Le défi étant dans les pattes. Design du plateau inspiré des portes de salon Western.",
        },
        {
          position: 10,
          title: "Sculpture d’arbre",
          src: require("../assets/image/10.jpg"),
          lazySrc:require("../assets/image/thumbnails/10_tn.jpg"),
          content:
            "Sculpture en Tilleuil,avec un encadrement en noyer noir. Avec application d’epoxy verte.",
        },
        {
          position: 11,
          title: "Tabouret",
          src: require("../assets/image/11.jpg"),
          lazySrc:require("../assets/image/thumbnails/7_tn.jpg"),
          content:
            "Projet pour nous familiariser à la conception de gabarit pour réaliser les pièces de l'assemblage.",
        },
      ],
    };
  },
};
</script>

<style lang="sass" scoped>
.container
    background-color: #ECE7DC
h2
    color: #947B47
    font-size: 2rem
p
    font-size: 1.25rem
    text-align: center
    width: 45%

@media (max-width: 600px)
    .realisation-container-11
        margin-top: 7px
    .realisation-container-8
        margin-top: 7px
    .realisation-container-5
        margin-top: 7px
    .realisation-container-4
        margin-top: 10px
    .realisation-container-7
        margin-top: 10px
    .realisation-container-10
        margin-top: 10px
    .realisation-container-6
        margin-top: 15px
    .realisation-container-9
        margin-top: 15px
@media (min-width:600px) and (max-width: 960px)
    .realisation-container-11
        margin-top: 20px
    .realisation-container-8
        margin-top: 20px
    .realisation-container-5
        margin-top: 20px
    .realisation-container-4
        margin-top: 25px
    .realisation-container-7
        margin-top: 25px
    .realisation-container-10
        margin-top: 25px
    .realisation-container-6
        margin-top: 20px
    .realisation-container-9
        margin-top: 20px
@media (min-width:960px) and (max-width: 1264px)
    .realisation-container-11
        margin-top: 25px
    .realisation-container-8
        margin-top: 25px
    .realisation-container-5
        margin-top: 25px
    .realisation-container-4
        margin-top: 28px
    .realisation-container-7
        margin-top: 28px
    .realisation-container-10
        margin-top: 28px
    .realisation-container-6
        margin-top: 20px
    .realisation-container-9
        margin-top: 20px
@media (min-width:1264px) and (max-width: 1904px)
    .realisation-container-11
        margin-top: 36px
    .realisation-container-8
        margin-top: 36px
    .realisation-container-5
        margin-top: 36px
    .realisation-container-4
        margin-top: 45px
    .realisation-container-7
        margin-top: 45px
    .realisation-container-10
        margin-top: 45px
    .realisation-container-6
        margin-top: 45px
    .realisation-container-9
        margin-top: 45px
@media (min-width:1904px)
    .realisation-container-11
        margin-top: 42px
    .realisation-container-8
        margin-top: 42px
    .realisation-container-5
        margin-top: 42px
    .realisation-container-4
        margin-top: 52px
    .realisation-container-7
        margin-top: 52px
    .realisation-container-10
        margin-top: 52px
    .realisation-container-6
        margin-top: 45px
    .realisation-container-9
        margin-top: 45px


.realisation-container
    position: relative
    overflow: hidden
    border-radius: 3px
    box-shadow: 3px 5px 12px -5px rgba(0,0,0,0.75)
    & img
        margin-bottom: -10px

.realisation-container-hover
    position: absolute
    top: 0
    bottom: 0 
    background-color: rgba(0, 0, 0, 0.5)
    width: 100%
    height: 100%
    border-radius: 3px
    & h3
        color: #DFCC93
        font-size: 2rem
    & p 
        color : #DFCC93
        font-size: 1rem

.hover-enter-active
    animation: hoverEnter .3s

.hover-leave-to
    animation: hoverEnter .3s reverse

@keyframes hoverEnter
    from
        transform: translateY(800px)
      
    to
        transform: translateY(0)
</style>