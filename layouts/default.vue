<template>
  <v-app id="application">
    <!-- Header -->
    <v-app-bar
      id="header"
      app
      color="primary"
      clipped-left
    >
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <v-toolbar-title>Skyferia</v-toolbar-title>
      <v-spacer />
      <v-btn icon>
        <v-icon>mdi-dots-vertical</v-icon>
      </v-btn>
    </v-app-bar>

    <!-- Navigation -->
    <v-navigation-drawer id="navigation" v-model="drawer" app clipped>
      <v-list
        dense
        nav
      >
        <v-subheader>
          NAVIGATION
        </v-subheader>
        <template
          v-for="nav in navs"
        >
          <v-list-group
            v-if="nav.subNavs"
            :key="nav.title"
            :prepend-icon="nav.icon"
            no-action
          >
            <template v-slot:activator>
              <v-list-item-content>
                <v-list-item-title v-text="nav.title" />
              </v-list-item-content>
            </template>

            <v-list-item
              v-for="subNav in nav.subNavs"
              :key="subNav.title"
              link
              :to="subNav.route"
            >
              <v-list-item-content>
                <v-list-item-title v-text="subNav.title" />
              </v-list-item-content>
              <v-list-item-icon>
                <v-icon v-text="subNav.icon" />
              </v-list-item-icon>
            </v-list-item>
          </v-list-group>
          <v-list-item v-else :key="nav.title" link :to="nav.route">
            <v-list-item-icon>
              <v-icon v-text="nav.icon" />
            </v-list-item-icon>
            <v-list-item-content>
              <v-list-item-title v-text="nav.title" />
            </v-list-item-content>
          </v-list-item>
        </template>
        <v-subheader>SUJETS SUIVIS</v-subheader>
        <v-list-item>
          <v-list-item-content>
            <v-list-item-title>Aucun actuellement.</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <v-subheader>CHATBOX</v-subheader>
        <v-list-item>
          <v-list-item-content two-line>
            <v-list-item-title class="mb-2">
              23 personnes connectées.
            </v-list-item-title>
            <v-btn color="secondary">
              Rejoindre
            </v-btn>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <!-- Content -->
    <v-content id="content">
      <v-container>
        <router-view />
      </v-container>
    </v-content>

    <!-- Footer -->
    <v-footer app>
      <span class="caption">© Copyright - 2020</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data: () => ({
    drawer: true,
    navs: [
      {
        slug: 'homepage',
        title: 'Accueil',
        icon: 'mdi-newspaper-variant-outline',
        route: '/accueil'
      },
      {
        slug: 'boardgame',
        title: 'Le Jeu',
        icon: 'mdi-atom-variant',
        route: '/jouer',
        subNavs: [
          {
            title: 'Carte du système',
            icon: 'mdi-compass-outline',
            route: '/jouer/carte'
          },
          {
            title: 'Vaisseau personnel',
            icon: 'mdi-ship-wheel',
            route: '/jouer/vaisseau'
          },
          {
            title: 'Fiche économique',
            icon: 'mdi-finance',
            route: '/jouer/economie'
          }
        ]
      },
      {
        slug: 'character',
        title: 'Personnage',
        icon: 'mdi-dna',
        route: '/personnage',
        subNavs: [
          {
            title: 'Profil',
            icon: 'mdi-human-handsdown',
            route: '/personnage/feuille'
          },
          {
            title: 'Inventaire',
            icon: 'mdi-package-variant',
            route: '/personnage/inventaire'
          },
          {
            title: 'Compétences',
            icon: 'mdi-source-fork',
            route: '/personnage/competences'
          },
          {
            title: 'Pouvoirs',
            icon: 'mdi-fire',
            route: '/personnage/pouvoirs'
          }
        ]
      },
      {
        slug: 'forum',
        title: 'Forum',
        icon: 'mdi-forum-outline',
        route: '/forum'
      },
      {
        slug: 'wiki',
        title: 'Univers',
        icon: 'mdi-book-open-outline',
        route: '/univers'
      }
    ]
  })
}
</script>
