<template>
  <v-app>
    <v-navigation-drawer v-model="draw" app>
      <v-list-item>
        <v-list-item-content>
          <v-list-item-title class="title">
            Application
          </v-list-item-title>
          <v-list-item-subtitle>
            subtext
          </v-list-item-subtitle>
        </v-list-item-content>
      </v-list-item>

      <v-divider></v-divider>

      <v-list dense nav>
        <v-list-item v-for="item in items" :key="item.title" link>
          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar app>
      <v-row class="px-8">
        <v-toolbar-title class="mr-5 mx-2">
          <nuxt-link to="/"> <img :src="logo" style="width:200px"/></nuxt-link>
        </v-toolbar-title>
        <v-toolbar-items v-show="$vuetify.breakpoint.mdAndUp">
          <v-btn v-for="i in list" :key="i" text>{{ i }}</v-btn>
        </v-toolbar-items>
        <v-spacer />
        <v-toolbar-items>
          <v-app-bar-nav-icon
            v-show="!$vuetify.breakpoint.mdAndUp"
            @click="draw = !draw"
          />
        </v-toolbar-items>
        <v-toolbar-items v-show="$vuetify.breakpoint.mdAndUp">
          <v-btn class="mx-1" outlined color="info">登入</v-btn>
          <v-btn class="mx-1" outlined color="info">註冊</v-btn>
        </v-toolbar-items>
      </v-row>
    </v-app-bar>
    <v-content>
      <nuxt />
    </v-content>

    <v-footer app absolute>
      <span>Yuntech Network Management. All rights reserved.</span>
      <v-spacer v-show="$vuetify.breakpoint.mdAndUp" />
      <span>&copy; {{ year }}</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  name: 'Default',
  data() {
    return {
      list: ['流量', '規範', '公告', '關於'],
      items: [
        { title: 'Dashboard', icon: 'dashboard' },
        { title: 'Account', icon: 'account_box' },
        { title: 'Admin', icon: 'gavel' }
      ],
      draw: null
    }
  },
  computed: {
    logo() {
      if (this.$vuetify.theme.dark)
        return 'https://zh.nuxtjs.org/logos/built-with-nuxt-white.svg'
      else return 'https://nuxtjs.org/logos/built-with-nuxt.svg'
    },
    year() {
      return new Date().getFullYear()
    }
  }
}
</script>
