<script>
  let inputValue = '';
  
  export { inputValue };
</script>

<template lang="pug">
div
  label(for="user-input") Enter text:
  input#user-input(
    type="text"
    bind:value="{inputValue}"
    placeholder="Type something here..."
  )
</template>

<style lang="stylus">
div
  margin 1rem 0

label
  display block
  margin-bottom 0.5rem
  font-weight bold
  color #333

input
  padding 0.75rem
  border 2px solid #dee2e6
  border-radius 4px
  width 100%
  max-width 400px
  font-size 1rem
  transition border-color 0.2s ease
  
  &:focus
    outline none
    border-color #4a90e2
    box-shadow 0 0 0 3px rgba(74, 144, 226, 0.1)
</style>