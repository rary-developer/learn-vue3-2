<template>
	<div></div>
</template>

<script>
import { reactive, ref } from "vue";

export default {
	setup() {
		// ref -> Object
		const count = ref(0);
		const state = reactive({
			count: count,
		});
		count.value++;
		count.value++;
		//console.log(count.value);
		console.log("state.count: ", state.count); //.value가 붙지 않는다.

		// ref -> Array
		const message = ref("Hello");
		const arr = reactive([message]);
		console.log("arr[0]: ", arr[0].value); //.value가 붙어야한다.

		return {};
	},
};
</script>

<style lang="scss" scoped></style>
