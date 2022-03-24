<template>
<section>
<array-card  :lists="list" v-for="list in lists"
:key="list.id"
:username ="lists.username"
:name="list.name"
:email="list.email"
:phone="list.phone"
:company="list.company.name"
:website="list.website"
:address="list.address.street"

  />
 <nuxt-link to="/users">users</nuxt-link>
 </section>
 </template>

<script>
import ArrayCard from  "../components/ArrayCard.vue"
export default{
components:{
     ArrayCard
    },
    data(){
      return{
lists:[]
      }},

  async fetch() {
      this.lists = await fetch(
        'https://jsonplaceholder.typicode.com/users'
      ).then(res => res.json())
    }
  
}
</script>
<style>
html{
  font-size:62.5%;
}
body{
  background-color: wheat;
}
@media only screen and (max-width:600px){
body{
  background-color:wheat;
}




}
</style>
