<script>
import AppHeader from "./components/AppHeader.vue";
import CardBirreria from "./components/CardBirreria.vue"

import axios from 'axios';
import {store} from './store.js';

export default {
	components: {
        AppHeader,
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
	}
}
</script>

<template>
    
    <AppHeader />
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
}
</style>