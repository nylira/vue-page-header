<template>
  <header :class="headerClass">
    <div class="ni-page-header-container">
      <h1 class="title">{{ title }}</h1>
      <p class="subtitle" v-if="subtitle" v-html="subtitle"></p>
      <slot></slot>
    </div>
  </header>
</template>

<script>
export default {
  name: 'ni-page-header',
  computed: {
    headerClass () {
      let value = 'ni-page-header '
      switch (this.type) {
        case 'center':
          value += 'ni-page-header-center'; break
        case 'split':
          value += 'ni-page-header-split'; break
        default:
          value += 'ni-page-header-default'
      }

      if (this.theme === 'tendermint') {
        value += ' ni-page-header-theme-tendermint'
      }

      return value
    }
  },
  props: ['title', 'subtitle', 'type', 'theme']
}
</script>

<style src="./style.css"></style>
