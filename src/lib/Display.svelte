<script>
  export let text = '';
  
  // Track what transformations were applied
  $: transformations = [];
  $: {
    transformations = [];
    if (text && text !== text.replace(/muk/gi, 'bang')) {
      transformations.push({ from: 'muk', to: 'bang' });
    }
    if (text && text !== text.replace(/cherry/gi, '🍒')) {
      transformations.push({ from: 'cherry', to: '🍒' });
    }
  }
</script>

{#if text}
  <div class="display-container">
    <h1>{text}</h1>
    {#if transformations.length > 0}
      <div class="transformations">
        <h3>Transformations Applied:</h3>
        <ul>
          {#each transformations as transform}
            <li>
              <strong>{transform.from}</strong>
              <span> → </span>
              <span>{transform.to}</span>
            </li>
          {/each}
        </ul>
      </div>
    {/if}
  </div>
{:else}
  <div class="display-container">
    <h1 class="placeholder">No text entered yet</h1>
  </div>
{/if}

<style lang="stylus">
.display-container
  margin 1rem 0
  padding 1rem
  border 2px solid #eee
  border-radius 8px
  background-color #f9f9f9

h1
  color #333
  font-size 2rem
  margin 0 0 1rem 0
  
  &.placeholder
    color #666
    font-style italic

.transformations
  background-color #e8f4f8
  padding 0.75rem
  border-radius 4px
  border-left 4px solid #4a90e2
  
  h3
    margin 0 0 0.5rem 0
    color #2c5aa0
    font-size 1rem
  
  ul
    margin 0
    padding-left 1.25rem
  
  li
    margin-bottom 0.25rem
  
  strong
    color #d73a49
    font-family monospace
  
  span
    color #28a745
    font-family monospace
</style>