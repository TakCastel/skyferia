<template>
  <v-layout align-center justify-center>
    <v-card>
      <v-toolbar color="primary">
        <v-toolbar-title>
          Connexion
        </v-toolbar-title>
        <v-spacer />
      </v-toolbar>
      <v-card-text>Formulaire de connexion.</v-card-text>
      <v-card-actions>
        <span class="caption">Vous n'avez pas de compte ?
          <a href="/register">Cliquez ici</a>
        </span>
      </v-card-actions>
    </v-card>
  </v-layout>
</template>

<script>
export default {
  layout: 'empty'
}
</script>
