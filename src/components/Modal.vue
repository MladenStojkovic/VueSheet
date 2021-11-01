<template>
  <modal :scrollable="true" height="auto" name="my-first-modal">

    <div class="bg-badin" v-if="action === 'frontEnd'">
      <div class="container">
        <div class="row">
          <div class="col-md-12 header">
            <p>Skillset</p>
            <p> Grade </p>
          </div>

          <div class="col-md-12 grade">
            <p>html</p>
            <p>  {{row[7]}} </p>
          </div>

          <div class="col-md-12 grade">
            <p>css</p>
            <p>  {{row[8]}} </p>
          </div>

          <div class="col-md-12 grade">
            <p>scss</p>
            <p>  {{row[9]}} </p>
          </div>

          <div class="col-md-12 grade">
            <p>less</p>
            <p>  {{row[10]}} </p>
          </div>

          <div class="col-md-12 grade">
            <p>bootstrap</p>
            <p>  {{row[11]}} </p>
          </div>

          <div class="col-md-12 grade">
            <p>javascript</p>
            <p>  {{row[12]}} </p>
          </div>

          <div class="col-md-12 grade">
            <p>jQuery</p>
            <p>  {{row[13]}} </p>
          </div>

          <div class="col-md-12 grade">
            <p>angular</p>
            <p>  {{row[14]}} </p>
          </div>

          <div class="col-md-12 grade">
            <p>react</p>
            <p>  {{row[15]}} </p>
          </div>

          <div class="col-md-12 grade">
            <p>vue</p>
            <p>  {{row[16]}} </p>
          </div>

          <div class="col-md-12 grade">
            <p>svelte</p>
            <p>  {{row[17]}} </p>
          </div>

          <div class="col-md-12 grade">
            <p>npm</p>
            <p>  {{row[18]}} </p>
          </div>

          <div class="col-md-12 grade">
            <p>yarn</p>
            <p>  {{row[19]}} </p>
          </div>

          <div class="col-md-12 grade">
            <p>typescript</p>
            <p>  {{row[20]}} </p>
          </div>

          <div class="col-md-12 grade">
            <p>vuex</p>
            <p>  {{row[21]}} </p>
          </div>

          <div class="col-md-12 grade">
            <p>redux</p>
            <p>  {{row[22]}} </p>
          </div>

          <div class="col-md-12 grade">
            <p>utest</p>
            <p>  {{row[23]}} </p>
          </div>

          <div class="col-md-12 grade">
            <p>design tools</p>
            <p>  {{row[24]}} </p>
          </div>
        </div>
      </div>
    </div>


    <div class="bg-badin" v-if="action === 'backEnd'">
      <div class="container">
        <div class="row">

          <div class="col-md-12 header">
            <p>Skillset</p>
            <p> Grade </p>
          </div>

          <div class="col-md-12 grade">
            <p>C#</p>
            <p>  {{row[25]}} </p>
          </div>

          <div class="col-md-12 grade">
            <p>Java</p>
            <p>  {{row[26]}} </p>
          </div>

          <div class="col-md-12 grade">
            <p>Node</p>
            <p>  {{row[27]}} </p>
          </div>

          <div class="col-md-12 grade">
            <p>PHP</p>
            <p>  {{row[28]}} </p>
          </div>

          <div class="col-md-12 grade">
            <p>MySQL</p>
            <p>  {{row[29]}} </p>
          </div>

          <div class="col-md-12 grade">
            <p>NoSQL</p>
            <p>  {{row[30]}} </p>
          </div>

        </div>
      </div>
    </div>

    <div class="bg-badin" v-if="action === 'qa'">
      <div class="container">
        <div class="row">

          <div class="col-md-12 header">
            <p>Skillset</p>
            <p> Grade </p>
          </div>

          <div class="col-md-12 grade">
            <p>jMeter</p>
            <p>  {{row[31]}} </p>
          </div>

          <div class="col-md-12 grade">
            <p>Postman</p>
            <p>  {{row[32]}} </p>
          </div>

          <div class="col-md-12 grade">
            <p>Selenium</p>
            <p>  {{row[33]}} </p>
          </div>

          <div class="col-md-12 grade">
            <p>Cypress</p>
            <p>  {{row[34]}} </p>
          </div>

        </div>
      </div>
    </div>

    <div class="bg-badin" v-if="action === 'devOps'">
      <div class="container">
        <div class="row">

          <div class="col-md-12 header">
            <p>Skillset</p>
            <p> Grade </p>
          </div>

          <div class="col-md-12 grade">
            <p>Jenkins</p>
            <p>  {{row[35]}} </p>
          </div>

          <div class="col-md-12 grade">
            <p>Git</p>
            <p>  {{row[36]}} </p>
          </div>

          <div class="col-md-12 grade">
            <p>Batch scripting</p>
            <p>  {{row[37]}} </p>
          </div>

          <div class="col-md-12 grade">
            <p>Bash scripting</p>
            <p>  {{row[38]}} </p>
          </div>

        </div>
      </div>
    </div>

    <div v-if="action === 'edit'">
      Dodati edit polja nakon svih skill-ova
    </div>

		</modal>
</template>

<script>
export default {
  props: {
    action: String,
    row: Array
  }
}
</script>

<style scoped>
.header {
  display: flex;
  justify-content: space-between;
  padding: 0.5rem 0;
  padding-left: 1rem;
  background-color: #075F89;
  color: rgba(255, 255, 255, 0.9);
  font-weight: bold;
}

.header p:nth-child(2) {
  text-align: center;
  width: 30%;
}

.grade {
  display: flex;
  justify-content: space-between;
  padding: 0;
  border-bottom: 1px solid rgba(255, 255, 255, 0.3);
  color: rgba(255, 255, 255, 0.9);
}

p {
  margin-bottom: 0;
}

.grade p:first-child {
  width: 70%;
  padding: 0.2rem 0;
  padding-left: 1rem;
  background-color: #0A7FB7;
  border-right: 1px solid rgba(255, 255, 255, 0.3);
}
.grade p:nth-child(2) {
  width: 30%;
  text-align: center;
  background-color: #238CBE;
}

.grade p:last-child {
  border-bottom: none;
}

</style>