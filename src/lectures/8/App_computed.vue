<template>
	<div>
		<h2>{{ teacher.name }}</h2>
		<h3>강의가 있습니까?</h3>
		<!-- <p>{{ teacher.lectures.length > 0 ? "있음!" : "없음!" }}</p> -->
		<p>{{ hasLecture }}</p>
		<p>{{ hasLecture }}</p>
		<p>{{ existLecture() }}</p>
		<p>{{ existLecture() }}</p>
		<button v-on:click="counter++">Counter : {{ counter }}</button>
		<h2>이름</h2>
		<p>{{ fullName }}</p>
	</div>
</template>

<script>
import { computed } from "vue";
import { reactive } from "vue";
import { ref } from "vue";

export default {
	setup() {
		const teacher = reactive({
			name: "김태희",
			lectures: ["HTML/CSS", "JavaScript", "Vue3"],
		});

		const hasLecture = computed(() => {
			//계산된 값이 캐싱됨
			console.log("computed"); //몇번 호출해도 한번만 나옴 (캐시로 변해서)
			return teacher.lectures.length > 0 ? "있음!" : "없음!";
		});

		const existLecture = () => {
			//메소드
			console.log("method");
			return teacher.lectures.length > 0 ? "있음!" : "없음!";
		};

		const counter = ref(0);

		const firstName = ref("홍");
		const lastName = ref("길동");

		const fullName = computed({
			//return firstName.value + " " + lastName.value;
			get() {
				return firstName.value + " " + lastName.value;
			},
			set(value) {
				console.log("value:", value);
				console.log(value.split(" "));
				[firstName.value, lastName.value] = value.split(" ");
			},
		});

		console.log("Console 출력:", fullName.value);
		fullName.value = "김 태희"; //readonly 경고
		return {
			teacher,
			hasLecture,
			existLecture,
			counter,
			firstName,
			lastName,
			fullName,
		};
	},
};
</script>

<style lang="scss" scoped></style>
