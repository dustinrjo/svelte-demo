<script>
  import UserInput from '$lib/UserInput.svelte';
  import Display from '$lib/Display.svelte';
  
  let userText = '';
  
  // Filter function to transform text
  function filterText(text) {
    if (!text) return '';
    return text
      .replace(/muk/gi, 'bang')
      .replace(/cherry/gi, '🍒');
  }
  
  // Reactive statement using Svelte's $: syntax
  $: filteredText = filterText(userText);
</script>

<template lang="pug">
div.app
  h1 Svelte Demo App
  
  UserInput(bind:inputValue="{userText}")
  
  div.debug-info
    p Raw input: "{userText}"
    p Filtered output: "{filteredText}"
  
  Display(text="{filteredText}")
</template>

<style lang="stylus">
.app
  max-width 600px
  margin 0 auto
  padding 2rem
  font-family Arial, sans-serif

h1
  text-align center
  color #333
  margin-bottom 2rem
  color salmon

.debug-info
  background-color #f8f9fa
  padding 1rem
  border-radius 4px
  margin 1rem 0
  border 1px solid #dee2e6
  
  p
    margin 0.5rem 0
    font-family monospace
    font-size 0.9rem
    color #495057
    
    &:first-child
      margin-top 0
    
    &:last-child
      margin-bottom 0
</style>
