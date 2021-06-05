
<template>
  <div class="slider-container">
    <div
      class="slider-item"
      v-for="(item, key) in posts"
      :key="key"
      :style="' z-index:' + item.positionZindex"
      v-show="showRealisationNumber === item.position"
    >
      <transition name="carousel">
        <img
          width="100%"
          height="100%"
          class="slider-item-image"
          :src="item.src"
          :alt="item.title"
          v-show="showRealisationNumber === item.position"
        />
      </transition>
      <transition name="text">
        <div
          v-if="showRealisationNumber === item.position"
          class="title-container"
        >
          <h3>{{ item.title }}</h3>
        </div>
      </transition>
      <transition name="text">
        <div
          v-if="showRealisationNumber === item.position"
          class="content-container"
        >
          <p>{{ item.content }}</p>
        </div>
      </transition>
    </div>
  </div>
</template>

<script>
export default {
  name: "Carousel",
  data() {
    return {};
  },
  props: ["posts", "showRealisationNumber", "showTransition"],
  methods: {
    generateRotate(element) {
      if (element === this.showRealisationNumber) {
        return 0;
      } else {
        return this.generIntRandom(-10, 10);
      }
    },
    generIntRandom(min, max) {
      return Math.floor(Math.random() * (max - min + 1)) + min;
    },
  },
};
</script>


<style lang="sass" scoped>
/* Color Theme Swatches in RGBA */
$grayMarronDark: rgba(98,90,101, 1)
$graylight: rgba(219,227,229, 1)
$graydark: rgba(143,157,165, 1)
$marronlight: rgba(179,158,139, 1)
$marronDark: rgba(115,74,60, 1)

.slider-container
  width: 100%
  height: 100%

.title-container
  position: absolute
  top: -100px
  width: 700px
  & h3
    text-align: center
    font-family: 'Playfair Display', serif
    font-style: italic
    font-weight: 400
    font-size: 3rem
    color: $graylight

.content-container
  position: absolute
  bottom: -85px
  width: 100%
  & p
    text-align: center
    font-family: 'Playfair Display', serif
    font-style: italic
    font-weight: 400
    font-size: 1.2rem
    color: $graylight

.slider-item
  position: absolute
  top: 0
  left: 0
  bottom: 0
  right: 0
  margin: auto
  width: 90%
  height: 90%
  & img
    object-fit: contain

.carousel-enter-active
  animation: carousel-in .8s ease

.carousel-leave-active
  animation: carousel-out .8s ease

.text-enter-active
  animation: text-in 0.4s linear

.text-leave-active
  animation: text-in 0.4s linear reverse

@keyframes carousel-in
  0%
    transform: scaleX(0)
  100%
    transform: scaleX(1)

@keyframes carousel-out
  0%
    transform: scaleX(1)
  100%
    transform: scaleX(0)

@keyframes text-in
  0%
    transform: scaleY(0)

  100%
    transform: scaleY(1)

@media (min-width: 1264px) and (max-width: 1786px)
  .title-container
    right: -10%

@media (min-width: 1786px) and (max-width: 1904px)
  .title-container
    right: 2.5%

@media (min-width: 1904px)
  .title-container
    right: 5%
</style>