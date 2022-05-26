<template lang="pug">
footer
  container
    row
      v-spacer
      v-btn(to='/', fab, nuxt, icon)
        v-avatar(size='48')
          v-img(
            :src='gravatar',
            alt='Icon'
          )
      v-spacer
    row
      v-spacer
      v-btn(
        v-for='(item, index) in icons',
        :key='index',
        icon,
        :href='item.url'
      )
        v-icon(large) {{ item.icon }}
      v-spacer
    row
      v-spacer
      small Website made with ❤️ by Asher and Ola
      v-spacer
    row
      v-spacer
      small Copyright &copy; {{ new Date().getFullYear() }},
        strong &nbsp; {{ copyright }}
      v-spacer
</template>

<script>
export default {
  data: () => ({
    copyright: '',
    icons: [
      // TODO: Fill with `social` datatype
    ],
    gravatar: ''
  }),
  async fetch() {
    const config = await this.$content('config').fetch()

    this.gravatar = `https://www.gravatar.com/avatar/${config.gravater_hash}?size=256r=g`
    this.copyright = config.copyright
  }
}
</script>
