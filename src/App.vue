<template lang="">
	<div>
		<Header />
		<Spinner v-if="!hasData" />
		<CryptoList v-else v-bind:crypts="cryptoData" />
	</div>
</template>
<script>
	import Header from './components/Header';
	import CryptoList from './components/CryptoList';
	import Spinner from './components/Spinner';
	import axios from 'axios';
	const API_KEY = 'ed599676c60cb5b0b369519d8cadaa8a';

	export default {
		data: () => ({
			cryptoData: []
		}),
		computed: {
			hasData() {
				return !!this.cryptoData.length; //Boolena to test if crypto info is loaded
			}
		},
		name: 'App',
		components: {
			Header,
			CryptoList,
			Spinner
		},
		mounted() {
			axios
				.get(`https://api.nomics.com/v1/currencies/ticker?key=${API_KEY}`, {
					params: {
						'per-page': '100',
						'page': 1,
						'rank': 1
					}
				})
				.then((response) => {
					this.cryptoData = response.data;
					console.log(response.data);
				})
				.catch(function(error) {
					console.log(error);
				});
		}
	};
</script>
<style>
	* {
		margin: 0;
		padding: 0;
		box-sizing: border-box;
		font-size: 16px;
	}
	body {
		font-family: 'Baloo 2', Helvetica, serif;
		font-weight: 400;
		color: #e7e7de;
		background-image: url('./img/background.jpg');
		background-repeat: no-repeat;
		background-attachment: fixed;
		background-size: cover;
	}
	[v-cloak] {
		display: none;
	}
</style>
