<template lang="">
	<div>
		<ul class="grid">
			<Crypto
				v-for="crypt in crypts"
				v-bind:cryptInfo="crypt"
				v-bind:key="crypt.id"
			></Crypto>
		</ul>
	</div>
</template>
<script>
	import Crypto from "./Crypto";
	export default {
		name: "CryptoList",
		components: {
			Crypto
		},
		props: ["crypts"]
	};
</script>
<style scoped>
	.grid {
		width: 80%;
		margin: 80px auto;
		display: flex;
		justify-content: center;
		flex-wrap: wrap;
		gap: 25px;
	}
</style>
