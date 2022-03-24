


<template>
    
     <div class='container' >
    <div class="image"><img :src="`https://avatars.dicebear.com/v2/avataaars/${user.username}.svg?options[mood][]=happy`" alt=""></div>
     <div class="userdata">
       <ul>
         <li><h1><b>{{user.name}}</b></h1></li>
         <li><b>email:</b> {{user.email }}</li>
         <li><b>phone:</b> {{user.phone}}</li>
         <li><b>company:</b> {{user.company.name}}</li>
         <li><b>website: </b>{{user.website}}</li>
         <li><b>address:</b> {{user.address.street}},{{user.address.suite}},{{user.address.city}},{{user.address.zipcode}}</li>
       </ul>
     </div>    
 </div>
   
</template>

<script>

import{mapState} from "vuex"

export default{
    computed:{
      user(){
          return this.$store.getters.getUserById(this.$route.params.users)
      }
    }
}
</script>

 <style scoped>
 
.container{
    margin: 6rem;
  
    margin-left: 6rem;
    box-shadow: 0 10px 10px 0;
    background-color: pink;
  


}
.image{
margin-left: 15rem;
  width :15rem;
  height: auto;

}
.userdata ul{
      list-style: none;
    text-align: center;
    font-size: 1.5rem;
 

  
}
@media  only screen and (max-width:600px){
.container {
      background-color: pink;
  
    height: 20rem;
    margin-top: 2rem;
    margin-left: 5.5rem;

}
.image{
      margin-left: 8rem;
    width: 7rem; 
}
.userdata ul{
  font-size: 1rem;

}



}



 </style>