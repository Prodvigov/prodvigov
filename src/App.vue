<template>
  
  <div id="app">
 
  <div>

    <Navbar />

    <b-container>

    <FormCheck />
  
    <div class="row justify-content-center">

    </div>

    <div class="row mb-5 mt-5">

    <Table />

  </div>

    </b-container>
  </div>
  </div>
</template>

<script>
import 'bootstrap/dist/css/bootstrap.css'
import 'bootstrap-vue/dist/bootstrap-vue.css'
import Navbar from '@/components/Navbar'
import FormCheck from '@/components/FormCheck'
import Table from '@/components/Table'

export default {
  name: 'app',
  components: {
    Navbar,
    FormCheck,
    Table
},
    data() {
      return {
        
      }
    }
  }
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

</style>
