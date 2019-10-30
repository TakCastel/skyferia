<template>
  <v-card>
    <v-card-title>{{ content.title }}</v-card-title>
    <v-card-text>{{ content.text }}</v-card-text>
  </v-card>
</template>

<script>
export default {
  props: {
    content: {
      type: Object,
      default: () => ({
        title: 'Titre de la news',
        text: 'Texte de la news'
      }),
      required: true
    }
  }
}
</script>
