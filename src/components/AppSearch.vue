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
        <input type="text" class="form-control" placeholder="Search your Film/Serie Tv"
        v-model.trim="store.searchText">
        <button 
        @click="$emit('mySelection')">
            SEARCH

            
        </button>

    </div>
</template>

<style lang="scss" scoped>
</style>