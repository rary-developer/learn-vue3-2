<template>
	<div>
		<p>{{ message }}</p>
		<p>{{ reverseMessage }}</p>
	</div>
</template>

<script>
import { ref, watch } from "vue";

export default {
	setup() {
		const message = ref("Hello Vue3");
		const reverseMessage = ref("");

		const reverseFunction = () => {
			console.log("즉시실행 함!");
			reverseMessage.value = message.value.split("").reverse().join("");
		};
		watch(
			message,
			//newValue => {
			// console.log("즉시실행 함!");
			// reverseMessage.value = newValue.split("").reverse().join("");
			//},
			// {
			// 	immediate: true,
			// },
			reverseFunction,
		);
		reverseFunction();

		return {
			message,
			reverseMessage,
			reverseFunction,
		};
	},
};
</script>

<style lang="scss" scoped></style>
