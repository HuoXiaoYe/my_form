<template>
	<span id="inp">
		<input :type="type" :value="value" @input="onInput" />
	</span>
</template>

<script>
	export default {
		name: "Input",
		props: {
			"type": {
				type: String,
				default: "text"
			},
			value: {
				"type": String,
				default: ""
			}
		},
		methods: {
			onInput(e) {
				this.$emit('input',e.target.value);
				this.$parent.$emit('validate')
			}
		}

	};
</script>
