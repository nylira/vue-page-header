<template>
  <header :class="headerClass">
    <div class="pz-page-header-container">
      <h1 class="title">{{ title }}</h1>
      <p class="subtitle" v-if="subtitle" v-html="subtitle"></p>
    </div>
  </header>
</template>

<script>
export default {
  name: 'pz-page-header',
  computed: {
    headerClass () {
      let value = 'pz-page-header '
      switch (this.type) {
        case 'center':
          value += 'pz-page-header-center'; break
        case 'split':
          value += 'pz-page-header-split'; break
        default:
          value += 'pz-page-header-default'
      }

      if (this.style === 'tendermint') {
        value += ' pz-page-header-tendermint'
      }

      return value
    }
  },
  props: ['title', 'subtitle', 'type', 'header-style']
}
</script>

<style src="./style.css"></style>
