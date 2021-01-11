<template lang="">
	<div>
		<li>
			<div class="card">
				<img v-bind:src="cryptInfo.logo_url" alt="Cryptocurrency Image" />
				<h3>{{ cryptInfo.name }}</h3>
				<h2>${{ cryptInfo.price }}</h2>
			</div>
		</li>
	</div>
</template>
<script>
	export default {
		name: "Crypto",
		props: ["cryptInfo"]
	};
</script>
<style scoped>
	li {
		list-style: none;
	}
	.card {
		display: flex;
		justify-content: center;
		align-items: center;
		flex-direction: column;
		width: 300px;
		height: 300px;
		padding: 25px;
		border-radius: 10px;
		background-color: teal;
	}
	h3 {
		text-transform: uppercase;
		font-size: 1.5rem;
		text-align: center;
	}
	h2 {
		font-size: 2.5rem;
	}
	img {
		width: 96px;
		height: 96px;
		margin: 20px auto;
	}
</style>
