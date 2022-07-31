<template>
	<div></div>
</template>

<script>
import { reactive, ref, watch } from "vue";

export default {
	setup() {
		const x = ref(0);
		const y = ref(0);

		const obj = reactive({
			count: 0,
		});

		// watch(
		// 	() => x.value + y.value,
		// 	(sum, oldValue) => {
		// 		console.log("sum: ", sum);
		// 		console.log("oldVaLUE: ", oldValue);
		// 	},
		// );

		//배열로 받기
		// watch([x, y], (newX, newY) => {
		// 	console.log("newX: ", newX);
		// 	console.log("newY: ", newX);
		// });

		//object
		// watch(
		// 	() => obj.count,
		// 	(newObj, olvObj) => {
		// 		console.log("newObj: ", newObj);
		// 	},
		// );

		// watch(obj, (newObj, oldObj) => {
		// 	console.log("newObj: ", newObj);
		// 	console.log("oldObj: ", oldObj);
		// });

		const person = reactive({
			name: "홍길동",
			age: 30,
			hobby: "운동",
			obj: {
				count: 0,
			},
		});

		// watch(person, newValue => {
		// 	console.log("newValue: ", newValue);
		// });

		watch(
			() => person.obj,
			newValue => {
				console.log("newValue: ", newValue);
			},
		);

		return {
			x,
			y,
			obj,
			person,
		};
	},
};
</script>

<style lang="scss" scoped></style>
