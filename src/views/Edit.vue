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
		name: "EditRow",
		components: {
			Loading
		},
    props: {
      row: Object,
      rowIndex: Number
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
    mounted () {
      this.populateFields()
    },
		methods: {
			async addRow() {
				this.loading = true
				const doc = new GoogleSpreadsheet('1lei8ZdcTPPEP3DXpTMZHdGLCQyCr63adgJWL1LCe2zI');
				await doc.useServiceAccountAuth(creds);
				await doc.loadInfo(); 
				const sheet = doc.sheetsByIndex[0];
        const rows = await sheet.getRows({
					offset: 0
				})				
          rows[this.$props.rowIndex].devId = this.devId,
					rows[this.$props.rowIndex].name = this.name,
					rows[this.$props.rowIndex].position = this.position,
					rows[this.$props.rowIndex].seniority = this.seniority,
					rows[this.$props.rowIndex].updated = new Date().toLocaleString(),
					rows[this.$props.rowIndex].comment = this.comment,
					rows[this.$props.rowIndex].grade = this.grade,
					rows[this.$props.rowIndex].description = this.description,
					rows[this.$props.rowIndex].html = this.html,
					rows[this.$props.rowIndex].css = this.css,
					rows[this.$props.rowIndex].scss = this.scss,
					rows[this.$props.rowIndex].less = this.less,
					rows[this.$props.rowIndex].bootstrap = this.bootstrap,
					rows[this.$props.rowIndex].javascript = this.javascript,
					rows[this.$props.rowIndex].jQuery = this.jQuery,
					rows[this.$props.rowIndex].angular = this.angular,
					rows[this.$props.rowIndex].react = this.react,
					rows[this.$props.rowIndex].vue = this.vue,
					rows[this.$props.rowIndex].svelte = this.svelte,
					rows[this.$props.rowIndex].npm = this.npm,
					rows[this.$props.rowIndex].yarn = this.yarn,
					rows[this.$props.rowIndex].typescript = this.typescript,
					rows[this.$props.rowIndex].vuex = this.vuex,
					rows[this.$props.rowIndex].redux = this.redux,
					rows[this.$props.rowIndex].utest = this.utest,
					rows[this.$props.rowIndex].designtools = this.designtools,
					rows[this.$props.rowIndex].csharp = this.csharp,
					rows[this.$props.rowIndex].java = this.java,
					rows[this.$props.rowIndex].node = this.node,
					rows[this.$props.rowIndex].php = this.php,
					rows[this.$props.rowIndex].mysql = this.mysql,
					rows[this.$props.rowIndex].nosql = this.nosql,
					rows[this.$props.rowIndex].jmeter = this.jmeter,
					rows[this.$props.rowIndex].postman = this.postman,
					rows[this.$props.rowIndex].selenium = this.selenium,
					rows[this.$props.rowIndex].cypress = this.cypress,
					rows[this.$props.rowIndex].jenkins = this.jenkins,
					rows[this.$props.rowIndex].git = this.git,
					rows[this.$props.rowIndex].batch = this.batch,
					rows[this.$props.rowIndex].bash = this.bash,

          await rows[this.$props.rowIndex].save()

				this.message = "Row Edited!";
				this.showMsg = true;
				this.loading = false
				
			},
      populateFields () {
        this.devId = this.$props.row[0]
				this.name = this.$props.row[1]
				this.position = this.$props.row[2]
				this.seniority = this.$props.row[3]
				this.updated = this.$props.row[4]
				this.comment = this.$props.row[5]
				this.grade = this.$props.row[6]
				this.description = this.$props.row[7]
				this.html = this.$props.row[8]
				this.css = this.$props.row[9]
				this.scss = this.$props.row[10]
				this.less = this.$props.row[11]
				this.bootstrap = this.$props.row[12]
				this.javascript = this.$props.row[13]
				this.jQuery = this.$props.row[14]
				this.angular = this.$props.row[15]
				this.react = this.$props.row[16]
				this.vue = this.$props.row[17]
				this.svelte = this.$props.row[18]
				this.npm = this.$props.row[19]
				this.yarn = this.$props.row[20]
				this.typescript = this.$props.row[21]
				this.vuex = this.$props.row[22]
				this.redux = this.$props.row[23]
				this.utest = this.$props.row[24]
				this.designtools = this.$props.row[25]
				this.csharp = this.$props.row[26]
				this.java = this.$props.row[27]
				this.node = this.$props.row[28]
				this.php = this.$props.row[29]
				this.mysql = this.$props.row[30]
				this.nosql = this.$props.row[31]
				this.jmeter = this.$props.row[32]
				this.postman = this.$props.row[33]
				this.selenium = this.$props.row[34]
				this.cypress = this.$props.row[35]
				this.jenkins = this.$props.row[36]
				this.git = this.$props.row[37]
				this.batch = this.$props.row[38]
				this.bash = this.$props.row[39]
      }
		}
	}
</script>

<style scoped>

</style>
