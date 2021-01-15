<template lang="">
	<div>
		<div class="spinner-container">
			<orbit-spinner :animation-duration="1200" :size="350" :color="'#fff'" />
		</div>
	</div>
</template>
<script>
	import { OrbitSpinner } from "epic-spinners"; //Epic spinner package
	export default {
		name: "Spinner",
		components: {
			OrbitSpinner
		}
	};
</script>
<style scoped>
	.spinner-container {
		display: flex;
		justify-content: center;
		align-items: center;
	}
</style>
