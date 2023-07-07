<script>
import { store } from "./../store.js";
export default {
    name: "ProductCard",
    props: {
    details: Object,
    // dettagli: Object,
  },
  data() {
     return {
       store,
            
     }
  },
//   methods: {
//     transformVotesInStars(numero) {
//         "<i class='fa-solid fa-star'></i>" * numero
//     }
//   }
}
</script>

<!-- HTML -->
<template>
    
    <!-- blocco prodotto -->
    <div class="prod-card" bg-img>
        <div class="immagine-poster">
            <img :src="'https://image.tmdb.org/t/p/w342' + details.poster_path" alt="immagine poster">
        </div>

        <!-- PARTE CHE SI VEDE SULL HOVER -->
        <div class="card-details">
            

        
            <!-- <div class="img-card">
                <img :src="'https://image.tmdb.org/t/p/w342' + details.backdrop_path" alt="immagine film">
            </div> -->

            
            
            <div class="titolo-card">{{ details.title ? details.title : details.name }}</div>  
            <!-- .name per SERIE  -->

            <div class="titoloOriginale-card"><strong>Titolo originale: </strong>{{ details.original_title ? details.original_title : details.original_name }}</div>
            <!-- .original_name per SERIE  -->

            <div class="voto-card"><strong>Voto: </strong>
                <i v-for="star in Math.round(details.vote_average / 2)" class='fa-solid fa-star'></i>
            </div>
            <!-- .vote_average per SERIE  -->

            <!-- <div class="lingua-card">Lingua originale: {{ store.lingueDiCuiHoBandiere.includes(details.original_language) ? '../../public/' + details.original_language + '.png' : details.original_language }}</div> -->
            <!-- .original_language per SERIE  -->

            <span><strong>Lingua originale: </strong></span>
            <img class="bandiera"
            :src="store.lingueDiCuiHoBandiere.includes(details.original_language) ? '/' + details.original_language + '.png' : details.original_language" :alt="store.lingueDiCuiHoBandiere.includes(details.original_language) ? '/' + details.original_language + '.png' : details.original_language">

            <div class="overview-card"><strong>Overview: </strong>{{ details.overview}}</div>

        </div>
    </div>


</template>

<!-- STILE -->

<style scoped lang="scss">
.prod-card {
    border: 1px solid black;
    width: calc(100%/5 - 20px);
    margin-left: 10px;
    margin-right: 10px;
    margin-top: 10px;
    margin-bottom: 30px;
    height: 450px;
    position: relative;
    .img-card {
        width: 100%;
        img {
            width: 100%;
            height: 100%;
        }
    }
    
    .titolo-card {
        padding-top: 6px;
        height: 15%;
        text-align: center;
        font-weight: 900;
    }
    .bandiera {
        width: 30px;
        height: 20px;
    }
    i {
        color: yellow
    }
    .overview-card {
        font-size: 13px;
    }
    .card-details {
        height: 450px;
        width:  100%;
        background-color: rgba(0, 0, 0, 0.8);
        opacity:0;
        position: absolute;
        bottom: 0px;
        &:hover {
            opacity: 1;
        }
        
        
        
        
    }
    .immagine-poster {
    height: 100%;
    width: 100%;
     
    img {
        width:100%;
        height: 100%;}
    }
   
    
}
</style>