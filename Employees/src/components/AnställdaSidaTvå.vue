<script>
 
/* props register */
export default{
    props:['anställd'],

}
</script>
<template>
      <div class="main-container">

      <div v-for="employee in anställd" :key="employee.id" class="card-container">
                <div class="img-container">
                    <img :src="employee.avatar"  :alt="employee.first_name">
                </div>
                <div class="text-container">
                    <div class="text-section">
                        <h4>Namn: {{ employee.first_name }}</h4>
                        <h4>Efternamn: {{ employee.last_name}}</h4>
                        <h5>Email: <a href="mailto:{{ employee.email}}"> {{ employee.email}}</a></h5>

                    </div>
                </div>
        </div> 
      </div> 


    
  
  </template>
  
  <style scoped>
 
  
  </style>
  
