
<template>
  <div class="background-container" :style="'backgroudn-color:#'+color">

      <div></div>

      <div></div>

      <div></div>

      <div></div>

      <div></div>


      <div></div>

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
    & div
        width: 5%
        &:nth-child(1)
            position: absolute
            top: 0
            right: 65%
            height: 70%  
            border-left: 2px solid $graydark
        &:nth-child(2)
            position: absolute
            top: 0
            right: 55%
            height: 60%  
            border-left: 2px solid $graydark
        &:nth-child(3)
            position: absolute
            top: 0
            right: 45%
            height: 50%     
            border-left: 2px solid $graydark
        &:nth-child(4)
            position: absolute
            top: 0
            right: 35%
            height: 40%     
            border-left: 2px solid $graydark
        &:nth-child(5)
            position: absolute
            top: 0
            right: 25%
            height: 30%     
            border-left: 2px solid $graydark
            
        &:nth-child(6)
            position: absolute
            top: 65%
            right: 0
            width: 70%
            height: 5%
            border-bottom: 2px solid $graydark        
        &:nth-child(7)
            position: absolute
            height: 5%
            width: 60%
            right: 0
            top: 55%
            border-bottom: 2px solid $graydark        
        &:nth-child(8)
            position: absolute
            height: 5%
            width: 50%
            right: 0
            top: 45%
            border-bottom: 2px solid $graydark        
        &:nth-child(9)
            position: absolute
            height: 5%
            width: 40%
            right: 0
            top: 35%
            border-bottom: 2px solid $graydark
        &:last-child
            position: absolute
            height: 5%
            width: 30%
            right: 0
            top: 25%
            border-bottom: 2px solid $graydark         


            
    
            
</style>