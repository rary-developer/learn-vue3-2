<template>
	<div>
		<div class="card">
			<div class="card-body">
				<!-- type : news, notice -->
				<span class="badge bg-secondary">{{ typeName }}</span>
				<h5 class="card-title red mt-2">{{ title }}</h5>
				<p class="card-text">
					{{ contents }}
				</p>
				<a href="#" class="btn" :class="isLikeClass" @click="toggleLike"
					>좋아요</a
				>
				<!-- <br />
				{{ obj }} -->
			</div>
		</div>
	</div>
</template>

<script>
//import { ref, useCssModule } from "vue";

import { computed } from "vue";

export default {
	props: {
		type: {
			type: String,
			default: "news",
			validator: value => {
				return ["news", "notice"].includes(value);
			},
		},
		title: {
			type: String,
			required: true,
		},
		contents: {
			type: String,
			//required: true,
		},
		isLike: {
			type: Boolean,
			deault: false,
		},
		obj: {
			type: Object,
			default: () => {
				return {};
			},
		},
	},
	emits: ["toggleLike"],
	setup(props, context) {
		//console.log("props.title : ", props.title);
		const isLikeClass = computed(() =>
			props.isLike ? "btn-danger" : "btn-outline-danger",
		);
		const typeName = computed(() =>
			props.type === "news" ? "뉴스" : "공지사항",
		);
		// 하위 속성에서 상위 속성 변경하기 (불가능)
		const toggleLike = () => {
			// 	props.isLike = !props.isLike;
			//context.emit("changeTitle");
			context.emit("toggleLike");
		};

		//const style = useCssModule();
		//console.log("style: ", style);

		//console.log("AppCard setup()");

		//const color = ref("red");
		//color.value = "black";
		return {
			isLikeClass,
			typeName,
			toggleLike,
		};
	},
};
</script>

<style></style>

<!-- <style>
.red {
	color: v-bind(color) !important;
}
</style> -->
<!-- <style scoped>
.red {
	color: red;
}
</style> -->
<!-- <style module="classes">
.red {
	color: red;
}
</style> -->
