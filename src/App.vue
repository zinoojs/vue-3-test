<template>
   <div id="app">
     <AppHeader/>
     <!-- component -->
    <div class="h-100 w-full flex items-center justify-center bg-teal-lightest font-sans">
      <!-- <FilmHero/> -->
      <Calender/>
    </div>
     
   </div>
</template>
<script>
import AppHeader from "./components/AppHeader.vue"
import Calender from "./components/Calender.vue"
// import FilmHero from "./components/FilmHeros.vue"
export default {
    data() {
      return {
        
      }
    },
    
    components : {
      AppHeader,
      Calender
      // FilmHero
    }
}
</script>
<style scoped>

</style>