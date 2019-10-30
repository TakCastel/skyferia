<template>
  <v-layout align-center justify-center>
    <v-card>
      <v-toolbar color="primary">
        <v-toolbar-title>
          Inscription
        </v-toolbar-title>
        <v-spacer />
        <v-btn text @click.stop="$router.back()">
          Annuler
        </v-btn>
      </v-toolbar>
      <v-card-text>Formulaire de création de compte.</v-card-text>
    </v-card>
  </v-layout>
</template>

<script>
export default {
  layout: 'empty'
}
</script>
