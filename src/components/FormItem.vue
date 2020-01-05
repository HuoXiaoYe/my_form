<template>
	<div class="item">
		<label>{{label}}</label>
		<slot></slot>
		<p v-show="isErr">{{promptMessage}}</p>
	</div>
</template>

<script>
	export default {
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
		}
	}
</script>

<style>
</style>
