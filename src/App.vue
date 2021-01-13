<template lang="">
	<div>
		<Header />
		<Search v-on:word="onWordChange" />
		<CryptoList v-bind:crypts="cryptoData" />
	</div>
</template>
<script>
	import Header from "./components/Header";
	import Search from "./components/Search";
	import CryptoList from "./components/CryptoList";
	import axios from "axios";
	const API_KEY = "ed599676c60cb5b0b369519d8cadaa8a";

	export default {
		data: function() {
			return {
				cryptoData: []
			};
		},
		name: "App",
		components: {
			Header,
			Search,
			CryptoList
		},
		methods: {
			onWordChange: function(searchTerm) {
				console.log(searchTerm);
			}
		},
		mounted() {
			axios
				.get(`https://api.nomics.com/v1/currencies/ticker?key=${API_KEY}`, {
					params: {
						"per-page": "100",
						"page": 1,
						"interval": `1h,1d`
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
		font-family: "Baloo 2";
		font-weight: lighter;
		color: #e7e7de;
		background-image: url("./img/background.jpg");
		background-repeat: no-repeat;
		background-attachment: fixed;
		/* background: rgb(0, 136, 145);
		background: radial-gradient(
			circle,
			rgba(0, 136, 145, 1) 0%,
			rgba(15, 48, 87, 1) 100%
		); */
	}
</style>
