<template>
	<div>
		<div class="card">
			<div class="card-body">
				<!-- type : news, notice -->
				<span class="badge bg-secondary">{{
					type === "news" ? "뉴스" : "공지사항"
				}}</span>
				<h5 class="card-title red mt-2">{{ title }}</h5>
				<p class="card-text">
					{{ contents }}
				</p>
				<a v-if="isLike" href="#" class="btn btn-danger">좋아요</a>
				<a v-else href="#" class="btn btn-outline-danger">좋아요</a>
			</div>
		</div>
	</div>
</template>

<script>
//import { ref, useCssModule } from "vue";

export default {
	props: {
		type: {
			type: String,
			default: "news",
		},
		title: {
			type: String,
			required: true,
		},
		contents: {
			type: String,
			required: true,
		},
		isLike: {
			type: Boolean,
			deault: false,
		},
	},
	setup() {
		//const style = useCssModule();
		//console.log("style: ", style);

		//console.log("AppCard setup()");

		//const color = ref("red");
		//color.value = "black";
		return {};
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
