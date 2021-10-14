<template>
  <modal :scrollable="true" height="auto" name="my-first-modal">

    <div class="py-4" v-if="action === 'frontEnd'">
      <div class="container">
        <div class="row">
          <div class="col-md-4">
            <h3>html</h3>
            <input type="text" :value="row[7]" disabled>
          </div>

          <div class="col-md-4">
            <h3>css</h3>
            <input type="text" :value="row[8]" disabled>
          </div>

          <div class="col-md-4">
            <h3>scss</h3>
            <input type="text" :value="row[9]" disabled>
          </div>

          <div class="col-md-4">
            <h3>less</h3>
            <input type="text" :value="row[10]" disabled>
          </div>

          <div class="col-md-4">
            <h3>bootstrap</h3>
            <input type="text" :value="row[11]" disabled>
          </div>

          <div class="col-md-4">
            <h3>javascript</h3>
            <input type="text" :value="row[12]" disabled>
          </div>

          <div class="col-md-4">
            <h3>jQuery</h3>
            <input type="text" :value="row[13]" disabled>
          </div>

          <div class="col-md-4">
            <h3>angular</h3>
            <input type="text" :value="row[14]" disabled>
          </div>

          <div class="col-md-4">
            <h3>angular</h3>
            <input type="text" :value="row[15]" disabled>
          </div>

          <div class="col-md-4">
            <h3>vue</h3>
            <input type="text" :value="row[16]" disabled>
          </div>

          <div class="col-md-4">
            <h3>vue</h3>
            <input type="text" :value="row[17]" disabled>
          </div>

          <div class="col-md-4">
            <h3>npm</h3>
            <input type="text" :value="row[18]" disabled>
          </div>

          <div class="col-md-4">
            <h3>yarn</h3>
            <input type="text" :value="row[19]" disabled>
          </div>

          <div class="col-md-4">
            <h3>typescript</h3>
            <input type="text" :value="row[20]" disabled>
          </div>

          <div class="col-md-4">
            <h3>vuex</h3>
            <input type="text" :value="row[21]" disabled>
          </div>

          <div class="col-md-4">
            <h3>redux</h3>
            <input type="text" :value="row[22]" disabled>
          </div>

          <div class="col-md-4">
            <h3>utest</h3>
            <input type="text" :value="row[23]" disabled>
          </div>

          <div class="col-md-4">
            <h3>design tools</h3>
            <input type="text" :value="row[24]" disabled>
          </div>
        </div>
      </div>
    </div>


    <div v-if="action === 'backEnd'">
      Dodati BE skillset
    </div>

    <div v-if="action === 'qa'">
      Dodati QA skillset
    </div>

    <div v-if="action === 'devOps'">
      Dodati dev ops skillset
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

<style>

</style>