<script>
	import { scale } from 'svelte/transition';
  export let params = {}
  console.log(params)
  import {fade} from 'svelte/transition'
</script>

<style>
</style>

<div in:fade>
  Modding Wiki
</div>