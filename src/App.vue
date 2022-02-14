<template>
  <v-app>
    <v-main>
      <v-toolbar color="black">
        <v-toolbar-title>
          <span class="white--text">Vuetify Demo</span>
        </v-toolbar-title>
        <v-toolbar-items>
          <v-btn text color="white" v-for="item in menuItems" :key="item.title">
            <v-icon>{{ item.icon }}</v-icon>
            {{ item.title }}
          </v-btn>
        </v-toolbar-items>
        <v-spacer></v-spacer>
        <v-toolbar-items>
          <v-toolbar-items>
            <LoginDialog />
          </v-toolbar-items>
        </v-toolbar-items>
      </v-toolbar>
      <v-container>
        <ProductList />
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
import ProductList from './components/ProductList'
import LoginDialog from './components/LoginDialog'

export default {
  name: 'App',

  components: {
    ProductList,
    LoginDialog
  },

  data: () => ({
    menuItems: [
      { title: 'Home', icon: 'mdi-home' },
      { title: 'Cart', icon: 'mdi-cart' }
    ]
  })
}
</script>
