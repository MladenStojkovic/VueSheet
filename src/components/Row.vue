<template>
	<tr>
		<td> {{ row[0] }} </td>
		<td> {{ row[1] }} </td>
		<td> {{ row[2] }} </td>
		<td> {{ row[3] }} </td>
		<td> {{ row[4] }} </td>
		<td> {{ row[5] }} </td>
		<td> {{ row[6] }} </td>
		<td> {{ row[7] }} </td>
		<td class="table-icons">
			<v-icon class="ml-2" name="code" @click="emitClick('frontEnd')"/>
			<v-icon class="ml-2" name="terminal" @click="emitClick('backEnd')"/>
			<v-icon class="ml-2" name="clipboard-check" @click="emitClick('qa')"/>
			<v-icon class="ml-2" name="server" @click="emitClick('devOps')"/>
			<v-icon class="ml-2" name="edit" @click="emitClick('edit')"/>
		</td>
	</tr>
</template>

<script>
	export default {
		name: "Row",
		props: ["row", "rowIndex"],
		mounted () {
			console.log(this.row._rawData)
		},
		methods: {
			logRowData() {
				this.$props.row.forEach(element => {
					console.log(element._rawData)
				});
			},
			emitClick(val) {
				this.$emit('view-details', val, this.rowIndex)
			}
		}
	}
</script>

<style scoped>

.table-icons {
	display: flex;
	align-items: center;
	justify-content: flex-end;
}

.table-icons svg {
	transition: color 0.25s ease-in-out;
	cursor: pointer;
}

.table-icons svg:hover {
	color: lightskyblue;
}

</style>