<script>
import {ref} from 'vue'
import AnställdaSidaTvå from '../components/AnställdaSidaTvå.vue'

 export default{
components:{AnställdaSidaTvå},
   setup(){
    const anställd=ref([])
    const error=ref(null)
    const getdata=async()=>{
        try{
        let data= await fetch("https://reqres.in/api/users?page=2")
               if(!data.ok){
              throw Error("no data avaliable")
               }
               let jsonData=await data.json()
               anställd.value= jsonData.data

              // console.log(anställd.value)

            }
            catch(err){
                error.value=err.message
                console.log( error.value)
            }

           

  }

  getdata()
  return{anställd}      

}
 }
 </script>



<template>
  <div class="about">

    <main>
      <div class="top-container" >
 <div class="top-div">
    <img src="../assets/topImg.png">
    </div>
    <h1> Uptäck våra medarbetare och kundserviceteam</h1>

  </div>

    <AnställdaSidaTvå :anställd="anställd"/>
   
  </main>
  </div>
</template>

<style>

</style>
