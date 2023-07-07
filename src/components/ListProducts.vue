<script>
import ProductCard from './ProductCard.vue';
import { store } from "./../store.js";
export default {
  name: "ListProducts",
  components: {
    ProductCard
  },
  data() {
     return {
       store,
            
     }
  },
  mounted() {
    console.log("caricato");
  }
  
}
</script>

<!-- HTML -->
<template>
  <div class="container">
    <section class="products">

      <h1>--FILM--</h1>
      <hr>
      <div class="boxes">
        <!-- SEZIONE DEI FILM -->
        
        <ProductCard 
        v-for="(film,index) in store.filmArray"
        :key='index'
        :details="film"
        
        />
      </div>

      <h1>--SERIE TV--</h1>
      <hr>
      <div class="boxes">
        <!-- SEZIONE DELLE SERIE TV -->
        <ProductCard 
        v-for="(serie,index) in store.seriesArray"
        :key='index'
        :details="serie"
        />



      </div>   

    </section>
  </div>

</template>

<!-- STILE -->

<style scoped lang="scss">
.boxes {
    display: flex;
    flex-wrap: wrap;
}
.container {
    color: white;
    height: 100%;
}
hr {
  color: white;
}
h1 {
  text-align: center;
}
</style>