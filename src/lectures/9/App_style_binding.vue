<template>
	<div>
		<div :style="styleObject">
			Lorem ipsum dolor sit amet consectetur adipisicing elit. Ipsa officia
			sequi cum repudiandae quos est dolore, possimus alias. Excepturi ea alias
			dolorum nesciunt quaerat earum labore qui similique facere neque.
		</div>
		<button v-on:click="fontSize--">-</button>
		<button v-on:click="fontSize++">+</button>
	</div>
</template>

<script>
import { computed, ref } from "vue";
//import { reactive } from "vue";

export default {
	setup() {
		// const styleObject = reactive({
		// 	//camelCase
		// 	color: "red",
		// 	fontSize: "13px",
		// });
		const fontSize = ref(13);

		const styleObject = computed(() => {
			return {
				color: "red",
				fontSize: fontSize.value + "px",
			};
		});

		return {
			styleObject,
			fontSize,
		};
	},
};
</script>

<style lang="scss" scoped></style>
