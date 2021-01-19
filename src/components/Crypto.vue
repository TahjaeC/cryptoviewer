<template lang="">
	<div>
		<li>
			<div class="card">
				<div class="face front">
					<img v-bind:src="cryptInfo.logo_url" alt="Crypto Logo" />
					<h3>{{ cryptInfo.name }}</h3>
					<p>{{ price }}</p>
				</div>
				<div class="face back">
					<h4><span>Symbol :</span> {{ cryptInfo.symbol }}</h4>
					<hr />
					<h4><span>Market Cap :</span> {{ cap }}</h4>
					<hr />
					<h4><span>Maximum Supply :</span> {{ supply }}</h4>
					<hr />
					<h4><span>All Time High :</span> {{ high }}</h4>
				</div>
			</div>
		</li>
	</div>
</template>
<script>
	export default {
		name: "Crypto",
		data: function() {
			return {
				price: new Intl.NumberFormat("en-US", {
					style: "currency",
					currency: "USD",
					maximumSignificantDigits: 7
				}).format(this.cryptInfo.price),
				cap: new Intl.NumberFormat("en-US", {
					style: "currency",
					currency: "USD",
					maximumSignificantDigits: 7
				}).format(this.cryptInfo.market_cap),
				supply: new Intl.NumberFormat().format(this.cryptInfo.max_supply),
				high: new Intl.NumberFormat("en-US", {
					style: "currency",
					currency: "USD",
					maximumSignificantDigits: 7
				}).format(this.cryptInfo.high)
			};
		},
		props: ["cryptInfo"]
	};
</script>
<style scoped>
	li {
		list-style: none;
	}
	h3 {
		text-transform: uppercase;
		font-size: 1.3rem;
		text-align: center;
		margin-bottom: 20px;
		letter-spacing: 2px;
	}
	h4 {
		margin: 10px auto;
		font-size: 1.2rem;
	}
	p {
		font-size: 2rem;
	}
	span {
		font-size: 1.3rem;
	}
	img {
		width: 96px;
		height: 96px;
		margin: 20px auto;
	}
	.card {
		position: relative;
		width: 300px;
		height: 300px;
		perspective: 500px;
	}
	.card .face {
		position: absolute;
		width: 100%;
		height: 100%;
		background-color: rgba(0, 128, 128, 0.2);
		box-shadow: 10px 10px 10px rgba(46, 54, 0, 0.03);
		backdrop-filter: blur(15px);
		-webkit-backdrop-filter: blur(8px);
		-moz-backdrop-filter: blur(8px);
		border-radius: 10px;
		transform-style: preserve-3d;
		transition: 0.5s;
		backface-visibility: hidden;
		-moz-backface-visibility: hidden;
	}
	.front {
		display: flex;
		justify-content: center;
		align-items: center;
		flex-direction: column;
	}
	.card:hover .face.front {
		transform: rotateY(180deg);
	}
	.card .face.back {
		transform: rotateY(180deg);
		padding: 20px;
		text-align: center;
	}
	.card:hover .face.back {
		transform: rotateY(360deg);
	}
</style>
