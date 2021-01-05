<template lang="">
	<div>
		<div class="header-container">
			<img src="../img/logo.png" alt="BlockChain Logo" />
			<h1>CryptoViewer</h1>
		</div>
	</div>
</template>
<script>
	export default {
		name: "Header"
	};
</script>
<style scoped>
	.header-container {
		display: flex;
		align-items: center;
		margin: 30px;
	}
	img {
		margin-right: 10px;
		height: 96px;
		width: 96px;
	}
</style>
