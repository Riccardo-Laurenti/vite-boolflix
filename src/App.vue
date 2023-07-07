<script>
import ListProducts from './components/ListProducts.vue';
import AppSearch from './components/AppSearch.vue';
import { store } from "./store";
export default {
  components: {
    ListProducts,
    AppSearch,
  },
  data() {
    return {
      store,
    }
  },

}
</script>

<template>

  <header>
    

</template>

<style lang="scss">

@use './styles/partials/variables.scss' as *;
@use './styles/generals.scss' as *;


header {
  background-color: $primary;
  height: 50px;
  .container {
    display: flex;
    justify-content: space-between;
    align-items: center;
    width: 95%;
    height: 100%;
    margin: 0 auto;
    h1 {
    color: red;
    }
  }
  
}


main {
  background-color: grey;
  padding-bottom: 20px;
  overflow-y: auto;
  height: calc( 100vh - 50px );
 

}

</style>