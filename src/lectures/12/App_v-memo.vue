<template>
	<div>
		<div v-memo="[subscribers]">
			<p>subcribers: {{ subscribers }}</p>
			<p>views: {{ views }}</p>
			<p>likes: {{ likes }}</p>
		</div>
		<div>
			<p>subcribers: {{ subscribers }}</p>
			<p>views: {{ views }}</p>
			<p>likes: {{ likes }}</p>
		</div>
	</div>
	<button @click="subscribers++">Subs++</button>
	<button @click="views++">Views++</button>
	<button @click="likes++">Likes++</button>
</template>

<script>
import { ref } from "vue";

export default {
	setup() {
		const subscribers = ref(4000);
		const views = ref(400);
		const likes = ref(20);
		return {
			subscribers,
			views,
			likes,
		};
	},
};
</script>

<style lang="scss" scoped></style>
