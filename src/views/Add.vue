<template>
	<div class="container-fluid">
		<div class="row">
			<main role="main" class="col-md-12 ml-sm-auto col-lg-12 pt-3 px-4">
				<div class="container">
					<div class="d-flex justify-content-between flex-wrap flex-md-nowrap align-items-center pb-2 mt-3 ">
						<h4 class="mb-3">New row</h4>
						<div class="btn-toolbar mb-2 mb-md-0">
							<router-link to="/"  class="btn btn-sm mr-1 btn-outline-secondary">
								Back
							</router-link>
							<a 	href="https://docs.google.com/spreadsheets/d/1lei8ZdcTPPEP3DXpTMZHdGLCQyCr63adgJWL1LCe2zI/edit?usp=sharing" 
								class="btn btn-sm btn-outline-secondary"
								target="_blank">
							View Google Sheet
							</a>
						</div>
					</div>
					<div v-if="showMsg" class="alert alert-success alert-dismissible fade show" role="alert">
						{{message}}
						<button type="button" class="close" data-dismiss="alert" aria-label="Close">
							<span aria-hidden="true">&times;</span>
						</button>
					</div>
					<div class="col-md-12 order-md-1">
						<form @submit.prevent="addRow">
							<div class="row">
								<div class="col-md-3 mb-3">
									<label for="devId">devId</label>
									<input type="text" v-model="devId" class="form-control" id="devId" placeholder="devId" required>
								</div>
								<div class="col-md-3 mb-3">
									<label for="name">name</label>
									<input type="text" v-model="name" class="form-control" id="name" required>
								</div>
								<div class="col-md-3 mb-3">
									<label for="position">position</label>
									<input type="text" v-model="position" class="form-control" id="position" placeholder="1234 Main St" required>
								</div>
								<div class="col-md-3 mb-3">
									<label for="seniority">seniority</label>
									<input type="text" v-model="seniority" class="form-control" id="seniority" placeholder="ex: Algiers" required>
								</div>
								<div class="col-md-3 mb-3">
									<label for="dateFrom">dateFrom</label>
									<input type="text" v-model="dateFrom" class="form-control" id="dateFrom" required>
								</div>
								<div class="col-md-3 mb-3">
									<label for="dateTo">dateTo</label>
									<input type="text" v-model="dateTo" class="form-control" id="dateTo" required>
								</div>
								<div class="col-md-6 mb-3">
									<label for="comment">comment</label>
									<input type="text" v-model="comment" class="form-control" id="comment" required>
								</div>
								<div class="col-md-2 mb-3">
									<label for="grade">grade</label>
									<input type="text" v-model="grade" class="form-control" id="grade" required>
								</div>
								<div class="col-md-10 mb-3">
									<label for="description">description</label>
									<input type="text" v-model="description" class="form-control" id="description" required>
								</div>

								<div class="col-md-12">
									<h4 class="text-center">Skills</h4>
								</div>

								<div class="col-md-2 mb-3">
									<label for="html">html</label>
									<input type="text" v-model="html" class="form-control" id="html" required>
								</div>

								<div class="col-md-2 mb-3">
									<label for="css">css</label>
									<input type="text" v-model="css" class="form-control" id="css" required>
								</div>

								<div class="col-md-2 mb-3">
									<label for="scss">scss</label>
									<input type="text" v-model="scss" class="form-control" id="scss" required>
								</div>

								<div class="col-md-2 mb-3">
									<label for="less">less</label>
									<input type="text" v-model="less" class="form-control" id="less" required>
								</div>

								<div class="col-md-2 mb-3">
									<label for="bootstrap">bootstrap</label>
									<input type="text" v-model="bootstrap" class="form-control" id="bootstrap" required>
								</div>

								<div class="col-md-2 mb-3">
									<label for="javascript">javascript</label>
									<input type="text" v-model="javascript" class="form-control" id="javascript" required>
								</div>

								<div class="col-md-2 mb-3">
									<label for="jQuery">jQuery</label>
									<input type="text" v-model="jQuery" class="form-control" id="jQuery" required>
								</div>

								<div class="col-md-2 mb-3">
									<label for="angular">angular</label>
									<input type="text" v-model="angular" class="form-control" id="angular" required>
								</div>

								<div class="col-md-2 mb-3">
									<label for="react">react</label>
									<input type="text" v-model="react" class="form-control" id="react" required>
								</div>

								<div class="col-md-2 mb-3">
									<label for="vue">vue</label>
									<input type="text" v-model="vue" class="form-control" id="vue" required>
								</div>

								<div class="col-md-2 mb-3">
									<label for="svelte">svelte</label>
									<input type="text" v-model="svelte" class="form-control" id="svelte" required>
								</div>

								<div class="col-md-2 mb-3">
									<label for="npm">npm</label>
									<input type="text" v-model="npm" class="form-control" id="npm" required>
								</div>

								<div class="col-md-2 mb-3">
									<label for="yarn">yarn</label>
									<input type="text" v-model="yarn" class="form-control" id="yarn" required>
								</div>

								<div class="col-md-2 mb-3">
									<label for="typescript">typescript</label>
									<input type="text" v-model="typescript" class="form-control" id="typescript" required>
								</div>

								<div class="col-md-2 mb-3">
									<label for="vuex">vuex</label>
									<input type="text" v-model="vuex" class="form-control" id="vuex" required>
								</div>

								<div class="col-md-2 mb-3">
									<label for="redux">redux</label>
									<input type="text" v-model="redux" class="form-control" id="redux" required>
								</div>

								<div class="col-md-2 mb-3">
									<label for="utest">u-test</label>
									<input type="text" v-model="utest" class="form-control" id="utest" required>
								</div>

								<div class="col-md-2 mb-3">
									<label for="designtools">design-tools</label>
									<input type="text" v-model="designtools" class="form-control" id="designtools" required>
								</div>
								
								<div class="col-md-6">
									<label for="">.</label>
									<button class="btn btn-primary btn-block" type="submit">SUBMIT</button>
								</div>
								
							</div>		
						</form>
					</div>

					
				</div>
				
			</main>
		</div>
	</div>
</template>

<script>
	const { GoogleSpreadsheet } = require('google-spreadsheet');
	const creds = require('@/client_secret.json');
	export default {
		name: "AddRow",
		data() {
			return {
				devId: '',
				name: '',
				position: '',
				seniority: '',
				dateFrom: '',
				dateTo: '',
				comment : '',
				grade: '',
				description: '',
				html: '',
				css: '',
				scss: '',
				less: '',
				bootstrap: '',
				javascript: '',
				jQuery: '',
				angular: '',
				react: '',
				vue: '',
				svelte: '',
				npm: '',
				yarn: '',
				typescript: '',
				vuex: '',
				redux: '',
				utest: '',
				designtools: '',

				showMsg: false

			}
		},
		methods: {
			async addRow() {
				const newRow = {
					devId: this.devId,
					name: this.name,
					position: this.position,
					seniority: this.seniority,
					dateFrom: this.dateFrom,
					dateTo: this.dateTo,
					comment :this.comment,
					grade: this.grade,
					description: this.description,
					html: this.html,
					css: this.css,
					scss: this.scss,
					less: this.less,
					bootstrap: this.bootstrap,
					javascript: this.javascript,
					jQuery: this.jQuery,
					angular: this.angular,
					react: this.react,
					vue: this.vue,
					svelte: this.svelte,
					npm: this.npm,
					yarn: this.yarn,
					typescript: this.typescript,
					vuex: this.vuex,
					redux: this.redux,
					utest: this.utest,
					designtools: this.designtools,
				}

				const doc = new GoogleSpreadsheet('1lei8ZdcTPPEP3DXpTMZHdGLCQyCr63adgJWL1LCe2zI');
				await doc.useServiceAccountAuth(creds);
				await doc.loadInfo(); 
				const sheet = doc.sheetsByIndex[0];
				await sheet.addRow(newRow);
				
				this.devId = ''
				this.name = ''
				this.position = ''
				this.seniority = ''
				this.dateFrom = ''
				this.dateTo = ''
				this.comment = ''
				this.grade = ''
				this.description = ''
				this.html = ''
				this.css = ''
				this.scss = ''
				this.less = ''
				this.bootstrap = ''
				this.javascript = ''
				this.jQuery = ''
				this.angular = ''
				this.react = ''
				this.vue = ''
				this.svelte = ''
				this.npm = ''
				this.yarn = ''
				this.typescript = ''
				this.vuex = ''
				this.redux = ''
				this.utest = ''
				this.designtools = ''

				this.message = "New row added !";
				this.showMsg = true;

				
			}
		}
	}
</script>

<style scoped>

</style>
