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

<template>
  <div class="container">
    <section class="products">

      <h1>Film</h1>
      <hr>
      <div class="boxes">        
        <ProductCard 
        v-for="(film,index) in store.filmArray"
        :key='index'
        :details="film"
        
        />
      </div>

      <h1>Serie Tv</h1>
      <hr>
      <div class="boxes">
        <ProductCard 
        v-for="(serie,index) in store.seriesArray"
        :key='index'
        :details="serie"
        />



      </div>   

    </section>
  </div>

</template>



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
    width: 80px;
    text-align: center;
    margin: auto;
}

h1 {
  text-align: center;
}
</style>