<script>
import { RouterLink, RouterView } from 'vue-router'

import Anställda from './components/Anställda.vue';
 export default{
data(){
  return{
    name:"jesus",
    date:12,
        /* another method to add props */

    job:"lord",
    text:"i love it "

  }
},components:{Anställda}
}
</script>

<template>
  <header>

    <div class="wrapper">
     

      <footer id="footer">
        <RouterLink to="/" id="link">1</RouterLink>
        <RouterLink to="/about" id="link">2</RouterLink>
      </footer>
    </div>
  </header>
  <RouterView />
</template>

<style scoped>

 
</style>
