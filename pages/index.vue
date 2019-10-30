<template>
  <div>
    <h1>Landing page</h1>
    <p>Description du jeu</p>
    <v-btn color="primary" to="/login">
      Login
    </v-btn>
    <v-btn outlined color="primary" to="/register">
      Créer un compte
    </v-btn>
  </div>
</template>

<script>
export default {
  layout: 'empty'
}
</script>
