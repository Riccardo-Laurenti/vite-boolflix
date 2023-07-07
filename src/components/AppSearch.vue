<script>
import { store } from "./../store.js";
export default {
    name: "AppSearch",
    data() {
        return {
            store,
        }
    }
}
</script>

<template>
    <div class="input_and_bottom">
        <input type="text" class="form-control" placeholder="search"
        v-model.trim="store.searchText">
        <!-- il .trim serve ad eliminare gli spazi -->

        <button 
        @click="$emit('mySelection')">
            SEARCH

            
        </button>

    </div>
    
    
    


    <!-- <select name="archetypes" id="archetypes-select" v-model="store.chosenArchetype" @change="$emit('mySelection')">
        
        option che non viene presa in considerazione da v-model
        <option value=""> --Please choose an Archetype-- </option>
        <option v-for="(elemento,index) in store.archetypesArray" :value="elemento.archetype_name" :key="index">
        {{ elemento.archetype_name }}
        </option>
       
    </select> -->

</template>

<style lang="scss" scoped>
</style>