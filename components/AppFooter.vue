<template lang="pug">
footer
  small Website made with ❤️ by Asher and Ola
  small Copyright &copy; {{ new Date().getFullYear() }},
    strong &nbsp; {{ copyright }}
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
