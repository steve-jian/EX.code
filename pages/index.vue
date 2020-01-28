<template>
  <div>
    <v-btn @click="show">
      {{ this.$vuetify.theme.dark ? '開燈' : '關燈' }}
    </v-btn>
  </div>
</template>

<script>
export default {
  methods: {
    show() {
      this.$vuetify.theme.dark = !this.$vuetify.theme.dark
    },
    run() {
      alert('Hi')
    }
  }
}
</script>
