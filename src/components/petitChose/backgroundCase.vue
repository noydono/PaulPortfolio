
<template>
  <div class="background-container" :style="'backgroudn-color:#'+color">
      <div></div>
      <div></div>
      <div></div>
      <div></div>
  </div>
</template>

<script>
export default {
  name: "BackgroundCase",
  data() {
    return {};
  },
  props: ["color", ],
  
};
</script>


<style lang="sass" scoped>
/* Color Theme Swatches in RGBA */
$grayMarronDark: rgba(98,90,101, 1)
$graylight: rgba(219,227,229, 1)
$graydark: rgba(143,157,165, 0.3)
$marronlight: rgba(179,158,139, 1)
$marronDark: rgba(115,74,60, 1)


.background-container
    width: 100%
    height: 100%
    display: flex
    flex-direction: row
    justify-content: center
    & div
        width: 10%
        height: 100%   
        &:nth-child(1)
            border-left: 1px solid $graydark
        &:nth-child(2)
            border-left: 1px solid $graydark
        &:nth-child(3)
            border-left: 1px solid $graydark
        &:nth-child(4)
            border-left: 1px solid $graydark
            border-right: 1px solid $graydark
            
</style>