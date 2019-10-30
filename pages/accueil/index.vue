<template>
  <v-layout justify-center column>
    <v-flex v-for="annonce in annonces" :key="annonce.id" class="mb-4">
      <news-feed :content="annonce" />
    </v-flex>
  </v-layout>
</template>

<script>
import NewsFeed from '@/components/NewsFeed'

export default {
  components: {
    NewsFeed
  },
  data: () => ({
    annonces: [
      {
        title: 'News 1',
        text: 'Nouveauté par ici !'
      },
      {
        title: 'News deuxième',
        text: 'Céti pas beau ?'
      }
    ]
  })
}
</script>
