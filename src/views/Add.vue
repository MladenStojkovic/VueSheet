<template>
	<div class="container-fluid">
		<loading :active.sync="loading" 
        :is-full-page="true"/>
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
									<input type="text" v-model="position" class="form-control" id="position" required>
								</div>
								<div class="col-md-3 mb-3">
									<label for="seniority">seniority</label>
									<input type="text" v-model="seniority" class="form-control" id="seniority" required>
								</div>
								<!-- <div class="col-md-3 mb-3">
									<label for="updated">updated</label>
									<input type="text" v-model="updated" class="form-control" id="updated" required>
								</div> -->
								<div class="col-md-11 mb-3">
									<label for="comment">comment</label>
									<input type="text" v-model="comment" class="form-control" id="comment" required>
								</div>
								<div class="col-md-1 mb-3">
									<label for="grade">grade</label>
									<input type="text" v-model="grade" class="form-control" id="grade" required>
								</div>
								<div class="col-md-12 mb-3">
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

								<div class="col-md-2 mb-3">
									<label for="csharp">C#</label>
									<input type="text" v-model="csharp" class="form-control" id="csharp" required>
								</div>

								<div class="col-md-2 mb-3">
									<label for="java">Java</label>
									<input type="text" v-model="java" class="form-control" id="java" required>
								</div>

								<div class="col-md-2 mb-3">
									<label for="node">Node</label>
									<input type="text" v-model="node" class="form-control" id="node" required>
								</div>

								<div class="col-md-2 mb-3">
									<label for="php">PHP</label>
									<input type="text" v-model="php" class="form-control" id="php" required>
								</div>

								<div class="col-md-2 mb-3">
									<label for="mysql">MySQL</label>
									<input type="text" v-model="mysql" class="form-control" id="mysql" required>
								</div>

								<div class="col-md-2 mb-3">
									<label for="nosql">NoSQL</label>
									<input type="text" v-model="nosql" class="form-control" id="nosql" required>
								</div>

								<div class="col-md-2 mb-3">
									<label for="jmeter">jMeter</label>
									<input type="text" v-model="jmeter" class="form-control" id="jmeter" required>
								</div>

								<div class="col-md-2 mb-3">
									<label for="postman">Postman</label>
									<input type="text" v-model="postman" class="form-control" id="postman" required>
								</div>

								<div class="col-md-2 mb-3">
									<label for="selenium">Selenium</label>
									<input type="text" v-model="selenium" class="form-control" id="selenium" required>
								</div>

								<div class="col-md-2 mb-3">
									<label for="cypress">Cypress</label>
									<input type="text" v-model="cypress" class="form-control" id="cypress" required>
								</div>

								<div class="col-md-2 mb-3">
									<label for="jenkins">Jenkins</label>
									<input type="text" v-model="jenkins" class="form-control" id="jenkins" required>
								</div>

								<div class="col-md-2 mb-3">
									<label for="git">Git</label>
									<input type="text" v-model="git" class="form-control" id="git" required>
								</div>

								<div class="col-md-2 mb-3">
									<label for="batch">Batch Scripting</label>
									<input type="text" v-model="batch" class="form-control" id="batch" required>
								</div>

								<div class="col-md-2 mb-3">
									<label for="bash">Bash Scripting</label>
									<input type="text" v-model="bash" class="form-control" id="bash" required>
								</div>
								
								<div class="col-md-12 text-center">
									<div class="col-md-6">
										<label for="">.</label>
										<button class="btn btn-primary btn-block" type="submit">SUBMIT</button>
									</div>
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
	import Loading from 'vue-loading-overlay';
	import 'vue-loading-overlay/dist/vue-loading.css';
	const { GoogleSpreadsheet } = require('google-spreadsheet');
	const creds = require('@/client_secret.json');
	export default {
		name: "AddRow",
		components: {
			Loading
		},
		data() {
			return {
				devId: '',
				name: '',
				position: '',
				seniority: '',
				updated: '',
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
				csharp: '',
				java: '',
				node: '',
				php: '',
				mysql: '',
				nosql: '',
				jmeter: '',
				postman: '',
				selenium: '',
				cypress: '',
				jenkins: '',
				git: '',
				batch: '',
				bash: '',

				showMsg: false,
				loading: false

			}
		},
		methods: {
			async addRow() {
				this.loading = true
				const newRow = {
					devId: this.devId,
					name: this.name,
					position: this.position,
					seniority: this.seniority,
					updated: new Date().toLocaleString(),
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
					csharp: this.csharp,
					java: this.java,
					node: this.node,
					php: this.php,
					mysql: this.mysql,
					nosql: this.nosql,
					jmeter: this.jmeter,
					postman: this.postman,
					selenium: this.selenium,
					cypress: this.cypress,
					jenkins: this.jenkins,
					git: this.git,
					batch: this.batch,
					bash: this.bash,

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
				this.updated = ''
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
				this.csharp = ''
				this.java = ''
				this.node = ''
				this.php = ''
				this.mysql = ''
				this.nosql = ''
				this.jmeter = ''
				this.postman = ''
				this.selenium = ''
				this.cypress = ''
				this.jenkins = ''
				this.git = ''
				this.batch = ''
				this.bash = ''

				this.message = "New row added!";
				this.showMsg = true;
				this.loading = false
				
			}
		}
	}
</script>

<style scoped>

</style>
