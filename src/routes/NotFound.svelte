<script>
  import {fade} from 'svelte/transition'
</script>
<style>
  div{
    display:grid;
    height: 100%;
    place-items: start center;
  }
</style>

<div class="notfound" in:fade>
  PageNotFound
</div>