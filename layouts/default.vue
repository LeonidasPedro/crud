<template>
  <v-app>
    <v-navigation-drawer
      v-model="drawer"
      fixed
      app

    >
      <v-list>
        <v-list-item
          v-for="(item, i) in items"
          :key="i"
          :to="item.to"
          router
          exact
        >
          <v-list-item-action>
            <v-icon
            color="#009bb7">{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title v-text="item.title" />
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar
      :clipped-left="clipped"
      fixed
      app
      color="#009bb7"
    >
      <v-app-bar-nav-icon 
      @click.stop="drawer = !drawer"
      color="white" />
           <v-spacer></v-spacer>
          <v-img
            src="https://www.unochapeco.edu.br/static/data/portal/sites/banners/811.png"
            max-width="160px"
            style=" border-radius: 50px;
            margin-top:-1%">
          </v-img>
          <v-spacer></v-spacer>

      <v-btn icon>
        <v-icon color="white">mdi-bell-circle</v-icon>
      </v-btn>

      <v-btn icon>
        <v-icon color="white">mdi-email-outline</v-icon>
      </v-btn>

      <v-btn icon>
        <v-icon color="white">mdi-account</v-icon>
      </v-btn>
    </v-app-bar>
    <v-main>
      <v-container>
        <Nuxt />
      </v-container>
    </v-main>
    <v-footer
      :absolute="!fixed"
      app
    >
      <span>&copy; {{ new Date().getFullYear() }}</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  name: 'DefaultLayout',
  data () {
    return {
      drawer: false,      
      items: [
        {
          icon: 'mdi-apps',
          title: 'Welcome',
          to: '/'
        },
        {
          icon: 'mdi-account-circle',
          title: 'Cadastro',
          to: '/cadastro'
        }
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'Vuetify.js'
    }
  }
}
</script>
