<template>
  <div class="accueil">

    <BackgroundCase class="background" color="2F2C40"/>

    <div class="brand-container-1">
      <h1>Paul Dubois</h1>
    </div>
    <div class="brand-container-2">
      <h2>Ebeniste</h2>
    </div>

    <div class="img">
      <img
        loading="lazy"
        src="../assets/pexels-thijs-van-der-weide-1094767.webp"
      />
    </div>

    <DownArrow color="light"/>

  </div>
</template>
<script>
import DownArrow from './petitChose/downArrow'
import BackgroundCase from './petitChose/backgroundCase'
export default {
  name: "Accueil",
  data() {
    return {
      load: false,
    };
  },
  components:{
    DownArrow,
    BackgroundCase
  }
};
</script>

<style lang="sass" scoped>
/* Color Theme Swatches in RGBA */
$grayMarronDark: #F2F1E4
$graylight: #8C884F
$graydark: #BBBF45
$marronlight: #9BA649
$marronDark: #2F2C40

.background
  position: absolute
  top: 0
  z-index: 0
  
.brand-container-1, .brand-container-2
  display: block
  z-index: 2
  overflow: hidden

h1
  font-family: 'Playfair Display', serif
  font-style: italic
  font-weight: 400
  font-size: 7rem
  color: white
  animation: h1Load 3.5s ease

h2
  @extend h1

.accueil
  display: flex
  flex-direction: column
  justify-content: center
  align-items: center
  background-color: $marronDark
  width: 100%
  height: 100%
  & .img
    animation: imgLoad 1.5s ease
    position: absolute
    overflow: hidden
    height: 600px
    width: 500px
    z-index: 1
    & img
      position: absolute
      bottom: 0px
      left: 0px
      width: 100%
      height: 100%
      object-fit: none
      opacity: 0.8

@keyframes imgLoad
  0%
    height: 0px
    width: 800px
  50%
    height: 600px
    width: 800px

  100%
    width: 500px

@keyframes h1Load
  0%
    font-size: 5rem
    transform: translate(0px, 100%)

  50%
    font-size: 5rem
    transform: translate(0px, 0px)

  100%
    font-size: 7rem
</style>