<template>
	<div class="container-fluid">
		<div class="row">
			<main role="main" class="col-md-12 ml-sm-auto col-lg-12 pt-3 px-4">
				<div class="d-flex justify-content-between flex-wrap flex-md-nowrap align-items-center pb-2 mb-3 ">
					<h2>VueSheet List</h2>
					<select name="" id="" @change="switchView($event,	$event.target.selectedIndex)">
						<option :value="index" v-for="(rowHeader, index) in header" :key="index"> {{rowHeader}} </option>
					</select>
					<input type="text" v-model="filter">
					<div class="btn-toolbar mb-2 mb-md-0">
						<a 	href="https://docs.google.com/spreadsheets/d/1lei8ZdcTPPEP3DXpTMZHdGLCQyCr63adgJWL1LCe2zI/edit?usp=sharing" 
							class="btn btn-sm btn-outline-secondary"
							target="_blank">
						View Google Sheet
						</a>
					</div>
				</div>
				<div class="table-responsive">
				<table class="table table-striped ">
					<thead>
					<tr>
						<th v-for="(cell, index) in header" :key="index"> {{ cell }} </th>
					</tr>
					</thead>
					
					<tbody>
						<Row :key="row.devId" v-for="row in filteredData" :row="row" />
					</tbody>
				</table>
				</div>
			</main>
		</div>
	</div>
</template>
 
<script>
import Row from '@/components/Row.vue';
const { GoogleSpreadsheet } = require('google-spreadsheet');
const creds = require('@/client_secret.json');
	export default {
		name: "Sheet",
		components: {
			Row
		},
		props: ["sheet"],
		data() {
			return {
				rows: [],
				header: '',
				filterRowIndex: 0,
				filter: '',
				loading: true,
			}
		},
		computed: {
			filteredData() {
				if (this.filter) {
					return this.rows.filter(row => {
					const filter = this.filter.toLowerCase()
					return row[this.filterRowIndex].includes(filter)
				})
				} else return this.rows
			}
		},
		created() {
			this.accessSpreadSheet();
		},
		methods:{
			async accessSpreadSheet() {
				const doc = new GoogleSpreadsheet('1lei8ZdcTPPEP3DXpTMZHdGLCQyCr63adgJWL1LCe2zI');
				await doc.useServiceAccountAuth(creds);
				await doc.loadInfo(); 
				const sheet = doc.sheetsByIndex[0];
				const  rows = await sheet.getRows({
					offset: 0
				})
				const header = await sheet.headerValues
				this.header = header
				rows.forEach(row => {
					this.rows.push(row._rawData)
				})
				console.log(this.rows)
			},
			switchView(event, selectedIndex) {
				this.filterRowIndex = selectedIndex
			}
		}
	}
</script>

<style scoped>

</style>