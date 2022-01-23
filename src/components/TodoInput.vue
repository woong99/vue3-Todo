<template>
	<div class="container">
		<input
			type="text"
			class="form-control"
			v-model="newTodoItem"
			placeholder="Type what you have to do" />
		<button @click="addTodo()" class="btn btn-info">+</button>
	</div>
</template>
<script>
export default {
	data() {
		return {
			newTodoItem: '',
		};
	},
	methods: {
		addTodo() {
			if (this.newTodoItem !== '') {
				const value = this.newTodoItem && this.newTodoItem.trim();
				this.$emit('addTodo', value);
				this.clearInput();
			}
		},
		clearInput() {
			this.newTodoItem = '';
		},
	},
};
</script>
<style lang="scss" scoped>
.container {
	display: flex;
	.form-control {
		border: 0px;
		text-align: center;
	}
	.btn {
		width: 60px;
		color: white;
		font-size: 32px;
	}
}
</style>
