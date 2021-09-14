<template>
	<tr>
		<td v-for="(cell, index) in row" :key="index"> {{row[cell]}} </td>
		<td>{{row.phone}}</td>
		<td>{{row.activity}}</td>
		<td>{{row.city}}</td>
		{{ row }}
	</tr>
</template>

<script>
	export default {
		name: "Row",
		props: ["row"],
	}
	
</script>

<style scoped>

</style>