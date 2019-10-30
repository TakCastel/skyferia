<template>
  <v-layout column>
    <v-flex>
      <v-card>
        <v-toolbar dense color="secondary">
          <v-toolbar-title>
            Carte du système
          </v-toolbar-title>
        </v-toolbar>
        <v-card-text>
          Vous êtes actuellement sur : {{ currentLocation }}
        </v-card-text>
        <v-divider />
        <v-card-actions>
          <v-spacer />
          <v-btn color="secondary" text>
            Aller au forum
          </v-btn>
        </v-card-actions>
      </v-card>
    </v-flex>
    <v-flex align-self-center>
      <solar-system />
    </v-flex>
  </v-layout>
</template>

<script>
import SolarSystem from '@/components/SolarSystem'

export default {
  components: {
    SolarSystem
  },
  data: () => ({
    currentLocation: 'Mars'
  })
}
</script>
