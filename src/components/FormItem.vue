<template>
	<div class="item">
		<label>{{label}}</label>
		<slot></slot>
		<p v-show="isErr">{{promptMessage}}</p>
		<!-- {{myForm.rules}} -->
	</div>
</template>

<script>
	import Schema from 'async-validator'
	export default {
		inject: ["myForm"],
		props: {
			label: {
				type: String,
				required: true,
			},
			prop: {
				type: String,
				required: true,
			}
		},
		data() {
			return {
				isErr: false,
				promptMessage: ""
			}
		},
		mounted() {
			this.$on("validate", this.validator)
		},
		methods: {
			validator() {
				const rules = this.myForm.rules[this.prop]; // 规则
				const value = this.myForm.model[this.prop]; // 字段值

				const descriptor = {
					[this.prop]: rules
				};
				const schema = new Schema(descriptor);
				schema.validate({
					[this.prop]: value
				}, errors => {
					if (errors) {
						this.promptMessage = errors[0].message;
						this.isErr = true;
					} else {
						this.promptMessage = '';
						this.isErr = false;
					}
				})
			}
		}
	}
</script>

<style>
</style>
