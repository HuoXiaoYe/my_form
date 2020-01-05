<template>
	<div id="app">
		<!-- {{info.name}} -->
		<my-form :model="info" :rules="rules">
			<my-form-item label="用户名" prop="name">
				<my-input v-model="info.name"></my-input>
			</my-form-item>
		</my-form>
	</div>
</template>

<script>
	import MyInput from "./components/Input";
	import MyForm from "./components/Form";
	import MyFormItem from "./components/FormItem";
	export default {
		name: "app",
		components: {
			MyInput,
			MyForm,
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
