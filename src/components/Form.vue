<template>
	<div>
		<form action="">
			<slot></slot>
		</form>
		
	</div>
</template>

<script>
	export default {
		props: {
			model: {
				type: Object,
				required: true,
			},
			rules: {
				type: Object,
				required: true,
			}
		}
	}
</script>

<style>
</style>
