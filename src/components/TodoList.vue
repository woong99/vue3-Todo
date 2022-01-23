<template>
	<div class="container">
		<ul>
			<li v-for="(item, index) in propsdata" :key="item">
				<i class="fa fa-check"></i> {{ item }}
				<span class="removeBtn" @click="removeTodo(item, index)"><i class="fa fa-trash-o"></i></span>
			</li>
		</ul>
	</div>
</template>
<script>
export default {
	data() {
		return {};
	},
	props: ['propsdata'],

	methods: {
		removeTodo(item, index) {
			this.$emit('removeTodo', item, index);
		},
	},
};
</script>
<style lang="scss" scoped>
ul {
	padding-left: 0;
	li {
		display: flex;
		align-items: center;
		height: 50px;
		background-color: white;
		min-height: 50px;
		margin: 10px 0;
		border-radius: 5px;
		font-size: 20px;
		.fa-check {
			color: #62acde;
			font-size: 20px;
			margin: 0 10px;
		}
		.removeBtn {
			margin-left: auto;
			margin-right: 10px;
			color: #de4343;
		}
	}
}
</style>
