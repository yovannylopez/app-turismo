<template>
  <div>
    <v-layout row wrap>
      <v-flex xs12 sm6 md4 v-for="(sitio, index) in sitios" :key="index">
        <Sitios :info="sitio" />
      </v-flex>
    </v-layout>
  </div>
</template>

<script>
  import axios from 'axios'
  import Sitios from './Sitios'

  export default {
    components: {
      Sitios
    },
    data() {
      return {
        sitios: []
      }
    },
    mounted() {
      this.listarSitios()
    },
    methods: {
      listarSitios() {
        axios.get('http://localhost:3000/api/sitios?filter[include][departamento]')
          .then(response => {
            console.log(response)
            this.sitios = response.data
          })
      }
    }
  }
</script>
