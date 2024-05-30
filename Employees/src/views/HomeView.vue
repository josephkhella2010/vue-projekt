<script>
import {ref} from 'vue'
import Anställda from '../components/Anställda.vue'

 export default{
components:{Anställda},
   setup(){
    const anställd=ref([])
    const error=ref(null)
    const getdata=async()=>{
        try{
        let data= await fetch("https://reqres.in/api/users")
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
  <main>
<!--     <h1 class="title"> Velkommen till vår team</h1>
 -->   
 <div class="top-container" >
 <div class="top-div">
    <img src="../assets/topImg.png">
    </div>
    <h1> Uptäck våra medarbetare och kundserviceteam</h1>

  </div>


    <Anställda :anställd="anställd"/>
   
  </main>
</template>
