<template>
	<div class="container">
		<button class="btn" @click="clearTodo()">Clear All</button>
	</div>
</template>
<script>
export default {
	methods: {
		clearTodo() {
			this.$emit('removeAll');
		},
	},
};
</script>
<style lang="scss" scoped>
.btn {
	width: 100px;
	height: 50px;
	border-radius: 5px;
	background-color: white;
	color: red;
}
</style>
