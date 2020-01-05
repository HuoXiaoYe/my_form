<template>
	<div id="app">
		<h1>{{info.name}}</h1>
		<my-form-item label="姓名:" prop="name">
			<my-input type="text" v-model="info.name"></my-input>
		</my-form-item>
	</div>
</template>

<script>
	import MyInput from "./components/Input";
	import MyFormItem from "./components/FormItem.vue"
	export default {
		name: "app",
		components: {
			MyInput,
			MyFormItem
		},
		data() {
			return {
				info: {
					name: "霍小叶"
				},
				rules: {
					name: [{
						required: true,
						message: "请输入用户名"
					}],
				}
			}
		},
		mounted() {
			// this.$on("inpChange", this.handleInput)
		},

		methods: {
			// handleInput(v) {
			// 	this.name = v
			// }
		}

	};
</script>

<style>
</style>
