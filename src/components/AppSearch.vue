<script>
import { store } from "../store.js" 


export default {
    name: "AppSearch",
    data() {
        return {
            store
        }
    },
    methods: {
        search() {
            this.$emit("search");
            console.log("ciao")
        }
    },
}
</script>

<template>
    <div class="ml-50 mt-30"> 
        <input class="" placeholder="Cerca per nome" v-model="store.searchString" @keyup.enter="$emit('search')">
        <button @click="search">Cerca</button>
    </div>
</template>

<style scoped></style>