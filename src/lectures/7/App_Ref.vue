<template>
	<div>
		<p>{{ message }}</p>
		<button v-on:click="addMessage">add Click</button>
	</div>
</template>

<script>
//import { reactive } from "vue";
import { ref } from "vue";

export default {
	setup() {
		// let message = reactive({
		// 	value: "Hello Vue!",
		// });
		let message = ref("Hello Vue!");

		const addMessage = () => {
			message.value = message.value + "!";
		};
		console.log(message);

		return {
			message,
			addMessage,
		};
	},
};
</script>

<style lang="scss" scoped></style>
