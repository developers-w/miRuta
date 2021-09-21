<template>
  <div class="home" >
    <div  v-for="(destination, i) in destinations" :key="i" >
       <router-link :to="destination.slug">
         <h2>{{destination.name}}</h2>         
       </router-link>

       <figure>
         <router-link to="destination-name">
           <img :src="require(`@/assets/${destination.image}`)" :alt="destination.name">
         </router-link>
       </figure>

    </div>
   
  </div>
</template>

<script>
// @ is an alias to /src

import store from "@/store.js"


export default {
  name: "Home",
  components: {
   
  },
  data() {
    return {
      destinations:store.destinations
    }
  },
};
</script>
<style scoped>
  .home{
    max-width: 1400px;
    margin: 0 auto;
  }

  img{
    max-width: 200px;
  }

  .destinations{
    display: flex;
    justify-content: space-between;
  }
</style>