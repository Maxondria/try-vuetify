<template>
  <nav>
    <v-app-bar flat app>
      <v-app-bar-nav-icon
        class="grey--text"
        @click.stop="drawer = !drawer"
      ></v-app-bar-nav-icon>

      <v-toolbar-title class="text-uppercase grey--text">
        <span class="font-weight-light">Project</span>
        <span>Manager</span>
      </v-toolbar-title>

      <v-spacer></v-spacer>

      <v-btn text color="grey">
        <span>Sign Out</span>
        <v-icon right>mdi-exit-to-app</v-icon>
      </v-btn>
    </v-app-bar>

    <v-navigation-drawer dark v-model="drawer" app class="primary">
      <v-list nav>
        <v-list-item
          v-for="(link, index) in links"
          :key="index"
          link
          router
          :to="link.route"
        >
          <v-list-item-icon>
            <v-icon>{{ link.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title>{{ link.text }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
  </nav>
</template>

<script>
export default {
  name: 'Navbar.vue',

  data: () => ({
    drawer: false,
    links: [
      { icon: 'mdi-view-dashboard', text: 'Dashboard', route: '/' },
      { icon: 'mdi-folder', text: 'My Projects', route: '/projects' },
      { icon: 'mdi-account', text: 'Team', route: '/team' },
    ],
  }),
};
</script>
