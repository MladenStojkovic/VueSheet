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
			<span class="ml-2 table-prop" name="code" @click="emitClick('frontEnd')"> FE </span>
			<span class="ml-2 table-prop" name="terminal" @click="emitClick('backEnd')"> BE </span>
			<span class="ml-2 table-prop" name="clipboard-check" @click="emitClick('qa')"> QA </span>
			<span class="ml-2 table-prop" name="server" @click="emitClick('devOps')"> DO </span>
			<v-icon class="ml-2" name="edit" @click="emitEdit()"/>
			<v-icon class="ml-2" name="trash" @click="emitDelete()"/>
		</td>
	</tr>
</template>

<script>
	export default {
		name: "Row",
		props: ["row", "rowIndex"],
		methods: {
			emitClick(val) {
				this.$emit('view-details', val, this.rowIndex)
			},
			emitEdit() {
				this.$emit('edit', this.rowIndex)
			},
			emitDelete() {
				this.$emit('delete', this.rowIndex)
			}
		}
	}
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Share+Tech+Mono&display=swap');
.table-icons {
	display: flex;
	align-items: center;
	justify-content: flex-end;
}

.table-icons svg {
	padding-bottom: 3px;
	transition: color 0.25s ease-in-out;
}

.table-icons svg:hover {
	color: #238CBE;
	cursor: pointer;
}

.table-prop {
	font-family: 'Share Tech Mono', monospace;
	transition: color 0.25s ease-in-out;
	cursor: pointer;
}

.table-prop:hover {
	color: #238CBE;
}

</style>