<template>
  <div class="realisation">
    <BackgroundCase class="background" color="F2F1E4" />

    <div class="realisation-row ">
      <div class="realisation-container">
        <div class="prev">
          <div class="prev-circle">
            <div class="prev-letter-container" @click="prev">
              <span>V</span>
              <span>E</span>
              <span>R</span>
              <span>P</span>
            </div>
          </div>
          <div class="underline"></div>
        </div>
        <div class="realisation-container-content">
          <Carousel
          
            :posts="posts"
            :showRealisationNumber="showRealisationNumber"
          />
        </div>
        <div class="next">
          <div class="underline"></div>
          <div class="next-circle">
            <div class="next-letter-container" @click="next">
              <span>N</span>
              <span>E</span>
              <span>X</span>
              <span>T</span>
            </div>
          </div>
        </div>
      </div>
    </div>
    <DownArrow color="light"/>

  </div>
</template>

<script>
import Carousel from "./petitChose/carousell";
import DownArrow from './petitChose/downArrow'
import BackgroundCase from "./petitChose/backgroundCase";
export default {
  name: "Réalisation",
  components: {
    Carousel,
    DownArrow,
    BackgroundCase
  },
  data() {
    return {
      showTransition: false,
      showRealisationNumber: 1,
      posts: [
        {
          position: 1,
          positionZindex: 22,
          title: "Logo Kindred",
          src: require("../assets/realisation/1.jpg"),
          lazySrc: require("../assets/realisation/thumbnails/1_tn.jpg"),
          content:
            "Plaquette de bois meurisier, découpé et recouvert d’epoxy verte et incolore.",
        },
        {
          position: 2,
          positionZindex: 21,
          title: "Marqueterie Hollow Knight",
          src: require("../assets/realisation/2.jpg"),
          lazySrc: require("../assets/realisation/thumbnails/2_tn.jpg"),
          content:
            "Marqueterie effectuée avec le procéder de Boule. Dessin inspiré de jeu vidéo.",
        },
        {
          position: 3,
          positionZindex: 20,
          title: "Marqueterie Momonoké",
          src: require("../assets/realisation/3.jpg"),
          lazySrc: require("../assets/realisation/thumbnails/3_tn.jpg"),
          content:
            "Marqueterie inspirée de Film japonais. Essence du plaquage,noyer noir,meurisier,acajou.",
        },
        {
          position: 4,
          positionZindex: 19,
          title: "Projet de fin de formation",
          src: require("../assets/realisation/4.jpg"),
          lazySrc: require("../assets/realisation/thumbnails/4_tn.jpg"),
          content:
            "Meuble de style asiatqiue, pieds inspirés des arches Torii Japonaise. Portes usinés à la CNC,gardant des gravures representant des nuages.",
        },
        {
          position: 5,
          title: "Meuble de cuisine",
          positionZindex: 18,
          src: require("../assets/realisation/5.jpg"),
          lazySrc: require("../assets/realisation/thumbnails/5_tn.jpg"),
          content:
            "Meuble en particule stratifié noir mat. Comptoir en stratifié Bambou.",
        },
        {
          position: 6,
          positionZindex: 17,
          title: "Armoire à Pharmacie",
          src: require("../assets/realisation/6.webp"),
          lazySrc: require("../assets/realisation/thumbnails/6_tn.jpg"),
          content:
            "Premier meuble effectué, avec des outils manuels seulement. Sculpture de Totoro en tête du meuble.",
        },
        {
          position: 7,
          positionZindex: 16,
          title: "Modern 2.0",
          src: require("../assets/realisation/7.webp"),
          lazySrc: require("../assets/realisation/thumbnails/7_tn.jpg"),
          content:
            "Meuble retro effectuer en mélamine paqué meurisier, avec des alaises en  meurisier massif. Pattes en massif meurisier.",
        },
        {
          position: 8,
          positionZindex: 15,
          title: "Meuble commercial",
          src: require("../assets/realisation/8.webp"),
          lazySrc: require("../assets/realisation/thumbnails/8_tn.jpg"),
          content:
            "Mon plus gros meuble réalisé à date. En contreplaqué russe, plaquer en stratifié blanc et gris mat. Effectué pour d’autres filières du CFP.",
        },
        {
          position: 9,
          positionZindex: 14,
          title: "Table à pattes galbées",
          src: require("../assets/realisation/9.webp"),
          lazySrc: require("../assets/realisation/thumbnails/9_tn.jpg"),
          content:
            "Table effectuée en bois massif meurisier. Le défi étant dans les pattes. Design du plateau inspiré des portes de salon Western.",
        },
        {
          position: 10,
          positionZindex: 13,
          title: "Sculpture d’arbre",
          src: require("../assets/realisation/10.webp"),
          lazySrc: require("../assets/realisation/thumbnails/10_tn.jpg"),
          content:
            "Sculpture en Tilleuil,avec un encadrement en noyer noir. Avec application d’epoxy verte.",
        },
        {
          position: 11,
          positionZindex: 12,
          title: "Tabouret",
          src: require("../assets/realisation/11.webp"),
          lazySrc: require("../assets/realisation/thumbnails/7_tn.jpg"),
          content:
            "Projet pour nous familiariser à la conception de gabarit pour réaliser les pièces de l'assemblage.",
        },
      ],
    };
  },
  methods: {
    prev() {
      if (this.showRealisationNumber > 1) {
        this.showRealisationNumber--;
        this.showTransitionTrueAndFalse();
        this.moveImagePrev();
      }
    },
    next() {
      if (this.showRealisationNumber < this.posts.length) {
        this.showRealisationNumber++;
        this.showTransitionTrueAndFalse();
        this.moveImageNext();
      }
    },
    showTransitionTrueAndFalse() {
      this.showTransition = true;
      setTimeout(this.showTransitionFalse, 1000);
    },
    moveImagePrev() {

      this.posts.forEach((e)=>{
        e.positionZindex--
        if(e.positionZindex < 12){
          e.positionZindex = 22
        }
      })
    },
    moveImageNext() {
      this.posts.forEach((e)=>{
        e.positionZindex++
        if(e.positionZindex > 22){
          e.positionZindex = 12
        }
      })
    },
  },
};
</script>

<style lang="sass" scoped>
$grayMarronDark: #F2F1E4
$graylight: #8C884F
$graydark: #BBBF45
$marronlight: #9BA649
$marronDark: #2F2C40

.background
  position: absolute
  top: 0
  
.realisation
  background-color: $marronDark
  width: 100%
  height: 100%
  display: flex
  flex-direction: column
  justify-content: center
  align-items: center

.realisation-row
  width: 50%
  height: 60%
  background-color: $marronDark
  
.realisation-container
  display: flex
  flex-direction: row
  justify-content: center
  align-content: center
  height: 100%
  width: 100%

.realisation-container-content
  position: relative
  height: 100%
  width: 100%
  background-color: rgba(0,0,0,0.3)
  box-shadow: -1px 2px 9px 1px rgba(140, 136, 79,0.15)
  border-radius: 3px

.carousel-enter-active
  animation: carousel 0.5s ease

.carousel-leave-active
  animation: carousel 0.2s ease reverse

@keyframes carousel
  0%
    transform: translateX(100%)

  100%
    transform: translateX(0)

.underline
  padding: 1px
  height: 1px
  width: 45px
  background-color: rgba(91, 87, 87 , 0.6 )

.prev
  display: flex
  flex-direction: row
  align-items: center
  height: 100%
  margin-right: -20px


.next
  display: flex
  flex-direction: row
  align-items: center
  justify-content: flex-end
  height: 100%
  margin-left: -20px
  margin-top: -1px


.prev-circle
  padding: 1px
  background-color: #8c8980
  height: 15px
  width: 15px
  border-radius: 50%
  position: relative
  cursor: pointer

.prev-letter-container
  width: 50px
  height: 50px
  margin-left: -20px
  margin-top: -20px
  font-family: 'Ubuntu', sans-serif
  user-select: none
  & span
    display: block
    font-weight: bold
    font-size: 0.8em
    position: absolute
    color: $grayMarronDark
    &:nth-child(1)
      transform: rotate(-9deg)
      top: -16px
      left: 0px
    &:nth-child(2)
      transform: rotate(-55deg)
      top: -10px
      left: -9px
    &:nth-child(3)
      transform: rotate(-100deg)
      top: 2px
      left: -12px
    &:nth-child(4)
      transform: rotate(-130deg)
      top: 12px
      left: -5px
  &:hover
    & span
      transition: all 0.1s linear
      &:nth-child(1)
        transform: rotate(0deg)
        top: -20px
        left: 2px
      &:nth-child(2)
        transform: rotate(-55deg)
        top: -14px
        left: -11px
      &:nth-child(3)
        transform: rotate(-100deg)
        top: 2px
        left: -15px
      &:nth-child(4)
        transform: rotate(-140deg)
        top: 15px
        left: -6px



.next-circle
  padding: 1px
  background-color: #8c8980
  height: 15px
  width: 15px
  border-radius: 50%
  position: relative
  cursor: pointer

.next-letter-container
  width: 50px
  height: 50px
  margin-left: -20px
  margin-top: -20px
  font-family: 'Ubuntu', sans-serif
  user-select: none
  & span
    display: block
    font-weight: bold
    font-size: 0.8em
    position: absolute
    color: $grayMarronDark
    &:nth-child(1)
      transform: rotate(35deg)
      top: -16px
      left: 12px
    &:nth-child(2)
      transform: rotate(65deg)
      top: -5px
      left: 20px
    &:nth-child(3)
      transform: rotate(110deg)
      top: 8px
      left: 19px
    &:nth-child(4)
        transform: rotate(155deg)
        top: 18px
        left: 11px
  &:hover
    & span
      transition: all 0.1s linear
      &:nth-child(1)
        transform: rotate(35deg)
        top: -20px
        left: 12px
      &:nth-child(2)
        transform: rotate(65deg)
        top: -7px
        left: 22px
      &:nth-child(3)
        transform: rotate(110deg)
        top: 9px
        left: 21px
      &:nth-child(4)
        transform: rotate(155deg)
        top: 21px
        left: 11px
</style>