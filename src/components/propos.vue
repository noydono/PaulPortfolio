<template>
  <div class="propos">

    <BackgroundCase class="background" color="F2F1E4" />

    <div class="propos-row">
      <div class="propos-col">
        <div class="propos-col-titre">
          <h2>Qui suis-je?</h2>
        </div>
        <div class="propos-col-content">
          <p>
            Je suis Paul Dubois, un français parti à l’aventure au Québec pour
            effectuer une formation d’ébéniste au CFP Alma (DEP d’ébéniste).
            Passioné par le travail du bois ainsi que par le dessin et la
            culture pop. La créativité demandée pour l’élaboration et la
            réalisation de meuble à été pour moi une source de motivation qui
            m’a poussé à me dépasser.
          </p>
        </div>
      </div>
      <DownArrow color="dark" style="margin-left: 1px;" />
    </div>
  </div>
</template>

<script>
import DownArrow from "./petitChose/downArrow.vue";
import BackgroundCase from "./petitChose/backgroundCase";
export default {
  components: { DownArrow, BackgroundCase },
  name: "Propos",
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
  z-index: 1

.propos
  background-color: $grayMarronDark
  width: 100%
  height: 100%
  display: flex
  flex-direction: column
  justify-content: center
  align-items: center

.propos-row
  display: flex
  flex-direction: column
  justify-content: center
  align-items: center
  border-radius: 3px
  width: 70%
  height: 90%

.propos-col
  display: flex
  flex-direction: column
  align-items: center
  width: 700px

.propos-col-titre
  color: $marronDark
  font-family: 'Playfair Display', serif
  font-style: regular
  font-size: 2em
  margin: 10px
  text-align: left
  width: 100%
  height: 100%

.propos-col-content
  display: flex
  flex-direction: row
  align-content: center
  justify-content: center
  & p
    color: $marronDark
    max-width: 650px
    margin: 20px 30px 20px 30px
    font-size: 1.75em
    font-family: 'Ubuntu', sans-serif
</style>