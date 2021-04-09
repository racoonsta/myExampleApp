<template>
  <a :href=generatePageLink(cardId)>
    <slot></slot>
  </a>
</template>

<script>
export default ({
  name: 'URLGenerator',
  props: {
    cardId: {
      required: true,
      type: Number
    }
  },
  methods: {
    generatePageLink (id) {
      const href = window.location.href
      return (`${href}${id}/index.html`)
    }
  }
})
</script>

<style lang="scss">
  .example__image {
    padding: 5px 5px;
    position: relative;
    display: block;
    max-width: 190px;
    height: 190px;
    border: 1px solid rgba(0,0,0, 0.5);
    border-radius: 5px;
  }
</style>
