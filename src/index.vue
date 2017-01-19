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
      let value = 'pz-page-header'
      if (this.type === 'center') {
        value += ' pz-page-header-center'
      } else if (this.type === 'split') {
        value += ' pz-page-header-split'
      } else {
        value += ' pz-page-header-default '
      }
      return value
    }
  },
  props: ['title', 'subtitle', 'type']
}
</script>

<style src="./style.css"></style>
