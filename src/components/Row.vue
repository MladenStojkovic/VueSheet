<template>
	<tr>
		<td v-for="(cell, index) in row" :key="index"> {{ cell }} </td>
	</tr>
</template>

<script>
	export default {
		name: "Row",
		props: ["row"],
		mounted () {
			console.log(this.row._rawData)
		},
		methods: {
			logRowData() {
				this.$props.row.forEach(element => {
					console.log(element._rawData)
				});
			}
		}
	}
</script>

<style scoped>

</style>