<script>
  export let subtopic
</script>

<style>
  /* your styles go here */
</style>

{#if subtopic == 'color'}
  scroll position: color
{:else if subtopic == 'birthcolor'}
  scroll position: birthcolor
{:else}
  everything
{/if}