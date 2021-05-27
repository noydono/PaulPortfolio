<template>
  <div>
      
    <v-app-bar v-if="drawer === false" fixed flat color="transparent" width="100px">
      <div class="burger mt-5" @click="drawer = true">
          <ul class="burger-list">
              <li class="burger-list-item"></li>
              <li class="burger-list-item"></li>
              <li class="burger-list-item"></li>
          </ul>
      </div>
    </v-app-bar>

    <v-navigation-drawer fixed v-model="drawer" color="rgba(191, 218, 131,0.5)" temporary>

      <v-list nav dense height="100vh" class="d-flex flex-column justify-center align-center">

        <h2 class="mb-5">Paul Dubois</h2>
        <div class="underline"></div>

        <v-list-item-group v-model="group" class="sidenav">

          <v-list-item class="text-center">
            <v-list-item-title class="body-1"><a style="text-decoration: none; color:black; font-size: 1.5rem;" href="#accueil" @click="drawer = false">Accueil</a></v-list-item-title>
          </v-list-item>

          <v-list-item class="text-center">
            <v-list-item-title class="body-1"><a style="text-decoration: none; color:black; font-size: 1.5rem;" href="#realisation" @click="drawer = false">Réalisation</a></v-list-item-title>
          </v-list-item>

           <v-list-item class="text-center">
            <v-list-item-title class="body-1"><a style="text-decoration: none; color:black; font-size: 1.5rem;" href="#contact" @click="drawer = false">Contact</a></v-list-item-title>
          </v-list-item>

        </v-list-item-group>
        <div class="underline"></div>

      </v-list>

    </v-navigation-drawer>
  </div>
</template>

<script>
export default {
  data: () => ({
    drawer: false,
    group: null,
  }),
};
</script>


<style lang="sass" scoped>

.underline
    background-color: black
    padding: 1px
    height: 1px   
    width: 105px
    
.burger
    background-color: #8D9D99 
    display: flex
    flex-direction: row
    justify-content: center
    border-radius: 50%
    width: 50px
    height: 50px
    cursor: pointer
    
.burger-list 
    list-style: none
    display: flex
    flex-direction: column
    justify-content: center
    align-items: center
    padding: 5px
    .burger-list-item
        padding:1px
        width: 20px
        background-color: #ECE7DC
        margin: 3px
        &:nth-child(2)
            width: 30px
            
</style>