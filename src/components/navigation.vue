<template>
  <div class="navigation-container">
    <ul class="navigation-container-list">
      <li class="navigation-container-list-item" :class="{ active: scrollPosition === 'accueil' }" >
        <div class="navigation-container-list-item__line" ></div>
        <a >Accueil</a>
      </li>
      <li class="navigation-container-list-item" :class="{ active: scrollPosition === 'propos' }" >
        <div class="navigation-container-list-item__line" ></div>
        <a >A Propos</a>
      </li>
       <li class="navigation-container-list-item" :class="{ active: scrollPosition === 'realisation' }" >
        <div class="navigation-container-list-item__line" ></div>
        <a >Realisation</a>
      </li>
      <li class="navigation-container-list-item" :class="{ active: scrollPosition === 'contact' }" >
        <div class="navigation-container-list-item__line" ></div>
        <a >Contact</a>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
    data(){
        return{
            isActive: this.scrollPosition
        }
    },
    props:{
        scrollPosition:String
    }
}
</script>

<style lang="sass" scoped>
/* Color Theme Swatches in RGBA */
$grayMarronDark: #F2F1E4
$graylight: #8C884F
$graydark: #BBBF45
$marronlight: #9BA649
$marronDark: #2F2C40

.navigation-container
    font-family: 'Playfair Display', serif
    & ul
        list-style: none
        & li 
            display: flex
            flex-direction: row
            justify-content: flex-start
            align-content: center
        & a
            text-decoration: none
            font-size: 20px
            font-weight: 600
            color: $graylight
            cursor: default
        & .navigation-container-list-item__line
            margin-top: 15px
            margin-right: 5px 
            height: 1px
            width: 30px
            background-color: $graylight
        & .active
            & a 
                color: $marronlight
            & .navigation-container-list-item__line
                margin-left: -20px
                width: 50px
                animation: active .3s
                background-color: $marronlight


@keyframes active
    from
        margin-left: 0
        width: 30px
    to
        margin-left: -20px
        width: 50px
</style>