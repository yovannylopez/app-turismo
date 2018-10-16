<template>
  <v-container fluid>
    <v-card >
      <v-card-title>
        <h2>
          <i class="material-icons">place</i> {{info.sitio | capitalize}}
        </h2>
      </v-card-title>
      <v-card-text>
        <p>{{info.descripcion}}</p>
      </v-card-text>
      <v-divider></v-divider>
      <v-card-actions class="pa-3">
        <i class="material-icons" color="primary">info</i>
        <h4>Departamento: {{info.departamento.departamento | capitalize}}</h4>
      </v-card-actions>
    </v-card>
  </v-container>
</template>

<script>
  export default {
    props: {
      info: {
        sitio: String,
        descripcion: String,
        departamento: String
      }
    },
    filters: {
      capitalize: function(value) {
        return value.charAt(0).toUpperCase() + value.slice(1)
      }
    }
  }
</script>

<style scoped>
h4 {
  padding-left: 0.5em;
}
i {
  color: purple;
}
p {
  text-align: justify;
}
</style>


