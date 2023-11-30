<script>

import CardBirreria from "./components/CardBirreria.vue"

import axios from 'axios';
import {store} from './store.js';

export default {
	components: {
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
				
				this.store.birrerie = risultato.data.results;
			});
		},
	}
}
</script>

<template>
    

	<main>
        
		<CardBirreria v-for="birreria in store.birrerie" :info="birreria" />
	</main>
</template>

<style scoped>

</style>