<template lang="">
	<div>
		<div class="search-container">
			<input
				type="text"
				placeholder="Search Crypto..."
				v-on:input="charInput"
			/>
		</div>
	</div>
</template>
<script>
	export default {
		name: "Search",
		methods: {
			charInput(event) {
				// console.log(event.target.value);
				this.$emit("word", event.target.value); //passes data up to the parent
			}
		}
	};
</script>
<style scoped>
	.search-container {
		display: flex;
		justify-content: center;
	}
	input {
		border: none;
		border-radius: 5px;
		width: 500px;
		height: 50px;
		padding: 10px;
		background-color: #e7e7de;
		font-family: "Baloo 2";
		font-size: 1.2rem;
	}
	::placeholder {
		font-family: "Baloo 2";
	}
</style>
