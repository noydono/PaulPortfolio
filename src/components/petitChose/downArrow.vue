<template>
  <svg
    width="24px"
    height="24px"
    xmlns="http://www.w3.org/2000/svg"
    fill-rule="evenodd"
    clip-rule="evenodd"
    :class="color"
  >
    <path
      d="M11 21.883l-6.235-7.527-.765.644 7.521 9 7.479-9-.764-.645-6.236 7.529v-21.884h-1v21.883z"
    />
  </svg>
</template>

<script>
export default {
    props:["color"]
}
</script>

<style lang="sass" scoped>
/* Color Theme Swatches in RGBA */
$grayMarronDark: #F2F1E4
$graylight: #8C884F
$graydark: #BBBF45
$marronlight: #9BA649
$marronDark: #2F2C40
svg
    z-index: 2
    position: absolute
    bottom: 5%
    animation: bounce 2s infinite
    margin-right: -3px
.dark
    fill: $marronDark
.light
    fill: $grayMarronDark

@keyframes bounce
    0%, 20%, 50%, 80%, 100%
        transform: translateY(0)
    40%
        transform: translateY(-30px)
    60%
        transform: translateY(-15px)
</style>
