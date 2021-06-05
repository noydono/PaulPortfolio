<template>
  <div class="contact-container">
    <BackgroundCase class="background" color="F2F1E4" />

    <div class="contact-row">
      <div class="contact-col">
        <div class="contact-col-titre">
          <h2>Contact</h2>
        </div>
        <div class="contact-col-content">
          <p>Pauldubois92@laposte.net</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import BackgroundCase from "./petitChose/backgroundCase";
export default {
  name: "contact",
  components: {
    BackgroundCase,
  },
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

.contact-container
    width: 100%
    height: 100%
    display: flex
    flex-direction: column
    justify-content: center
    align-items: center

.contact-row
    display: flex
    flex-direction: column
    justify-content: center
    align-items: center
    border-radius: 3px
    width: 70%
    height: 90%

.contact-col
    display: flex
    flex-direction: column
    align-items: center
    width: 700px

.contact-col-titre
    color: $marronDark
    font-family: 'Playfair Display', serif
    font-style: regular
    font-size: 2em
    margin: 10px
    text-align: center
    width: 100%
    height: 100%

.contact-col-content
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