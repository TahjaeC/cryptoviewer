<template lang="">
	<div class="container">
		<input type="text" placeholder="Search..." v-on:input="onInput" />
	</div>
</template>
<script>
	export default {
		name: 'Search',
		methods: {
			onInput: function(event) {
				// console.log(event.target.value); //Get chacracter input
				this.$emit('wordChange', event.target.value); //Passing data up to the App.vue
			}
		}
	};
</script>
<style scoped>
	.container {
		display: flex;
		justify-content: center;
		align-items: center;
	}
	input {
		margin-top: 50px;
		width: 400px;
		height: 45px;
		background-color: white;
		border-radius: 25px;
		padding-left: 15px;
		border: none;
		outline: none;
	}
	@media screen and (max-width: 768px) {
		input {
			width: 250px;
		}
	}
</style>
