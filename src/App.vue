<template>
	<TodoHeader />
	<TodoInput @addTodo="addTodo" />
	<TodoList :propsdata="todoItems" @removeTodo="removeItem" />
	<TodoFooter @removeAll="clearAll" />
</template>

<script>
import TodoHeader from '~/components/TodoHeader';
import TodoInput from '~/components/TodoInput';
import TodoList from '~/components/TodoList';
import TodoFooter from '~/components/TodoFooter';
export default {
	components: {
		TodoHeader,
		TodoInput,
		TodoList,
		TodoFooter,
	},
	data() {
		return {
			todoItems: [],
		};
	},

	created() {
		if (localStorage.length > 0) {
			for (let i = 0; i < localStorage.length; i++) {
				this.todoItems.push(localStorage.key(i));
			}
		}
	},
	methods: {
		addTodo(todoItem) {
			localStorage.setItem(todoItem, todoItem);
			this.todoItems.push(todoItem);
		},
		clearAll() {
			localStorage.clear();
			this.todoItems = [];
		},
		removeItem(item, index) {
			localStorage.removeItem(item);
			this.todoItems.splice(index, 1);
		},
	},
};
</script>
<style lang="scss">
@import '~/scss/main';
body {
	text-align: center;
	background-color: #f6f6f8;
	font-family: 'Ubuntu', sans-serif;
}
</style>
