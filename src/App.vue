<script>
import AppHeader from "./components/AppHeader.vue";
import AppSearch from "./components/AppSearch.vue";
import CardBirreria from "./components/CardBirreria.vue"

import axios from 'axios';
import {store} from './store.js';

export default {
	components: {
        AppHeader,
		AppSearch,
		CardBirreria
	},

	data() {
		return {
			store,
		}
	},
	mounted() {
		this.getBirrerie();
	},
	methods: {
		getBirrerie() {
			axios.get(this.store.apiUrl).then(risultato => {
				
				this.store.birrerie = risultato.data
			});
		},
		cerca (){
			let indirizzo = `${this.store.apiUrl}&by_name=${store.searchString}`;
			axios.get(indirizzo).then(risultato => {
				this.store.birrerie = risultato.data
				console.log(indirizzo)
			})
		}
	}
}
</script>

<template>
    
    <AppHeader />
	<AppSearch @search="cerca"/>
	<main>
		<CardBirreria v-for="birreria in this.store.birrerie" :info="birreria" />
	</main>
</template>

<style scoped>
main {
	width: 70%;
	margin: 50px auto;

	display: flex;
	flex-wrap: wrap;
    justify-content: center;
    align-items: center;
}
</style>