<template>
 <div class='container' @click="$router.push(`/users/${lists.id}`)">
    <div class="image"><img :src="`https://avatars.dicebear.com/v2/avataaars/${lists.username}.svg?options[mood][]=happy`" alt=""></div>
     <div class="userdata">
       <ul>
         <li><h1><b>{{lists.name}}</b></h1></li>
         <li><b>email:</b> {{lists.email }}</li>
         <li><b>phone:</b> {{lists.phone}}</li>
         <li><b>company:</b> {{lists.company.name}}</li>
         <li><b>website: </b>{{lists.website}}</li>
         <li><b>address:</b> {{lists.address.street}},{{lists.address.suite}},{{lists.address.city}},{{lists.address.zipcode}}</li>
       </ul>
     </div>
 </div>
  
</template>
<script>
  export default {
    
      props:{
      lists:{
          type:Object,
          required:true,
          },
 
   
  },


  }
</script>
<style scoped>

.container{

 justify-content: center;
margin-left:8.5rem;
  box-shadow: 0 2px 2px 0;
  background-color: white;



}
.image{
display: flex;
  width :10rem;
  height: auto;

}
.userdata ul{
  list-style: none;
  margin-top: -10rem;
font-size: 1.2rem;
  text-align: start;
  margin-left: 10rem;
  
}
@media  only screen and (max-width:600px){
.container {
  background-color:white;
  width:25rem;
  height: 14rem;
  margin-top:2rem;
 

}
.image{
  
  width:7rem;
  
}
.userdata ul{
  font-size: 1rem;
  margin-top:-20%;
  margin-left:6rem;
}



}






</style>