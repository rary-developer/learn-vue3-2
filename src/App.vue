<template>
	<div>
		<p>{{ counter }}</p>
		<p>{{ message }}</p>
		<button @click="increament">click</button>
	</div>
</template>

<script>
import { ref } from "vue";

export default {
	setup() {
		const counter = ref(0);
		const message = ref("Hello Vue3");
		const increament = () => {
			counter.value++;
		};

		return {
			counter,
			message,
			increament,
		};
	},
};
</script>

<style lang="scss" scoped></style>
