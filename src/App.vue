<template lang="">
	<div>
		<Header></Header>
		<Search v-on:word="onWordChange"></Search>
	</div>
</template>
<script>
	import Header from "./components/Header";
	import Search from "./components/Search";
	export default {
		name: "App",
		components: {
			Header,
			Search
		},
		methods: {
			onWordChange: function(searchTerm) {
				console.log(searchTerm);
			}
		}
	};
</script>
<style>
	* {
		margin: 0;
		padding: 0;
		box-sizing: border-box;
	}
	body {
		font-family: "Baloo 2";
		font-weight: lighter;
		color: #e7e7de;
		background: rgb(0, 136, 145);
		background: radial-gradient(
			circle,
			rgba(0, 136, 145, 1) 0%,
			rgba(15, 48, 87, 1) 100%
		);
	}
</style>
