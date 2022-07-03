<script>
	import NavButton from './../components/NavButton.svelte';
	import Button from './../components/Button.svelte';
  import {fade} from 'svelte/transition'
  import {push,pop,replace} from 'svelte-spa-router'
</script>

<style>
  .home{
    padding-inline:5rem
  }
  section{
    margin-block:1rem;
  }
  h1{
    display:flex;
    gap:0.5rem;
    justify-content: center;
    margin-bottom: 1rem;
  }
  :where(.gallery .image){
    width: 100%;
    border-radius: 0.5rem;
  }
  .project{
    display:flex;
    flex-direction: column;
    gap: calc(var(--round)*2);
    background: var(--gray-500);
    padding:1rem;
    border-radius: 0.5rem;
  }
  .gallery{
    display:grid;
    grid-template-columns: repeat(2, 1fr);
    gap:1rem;
  }
  @media(max-width:768px){
    .gallery{
      grid-template-columns: 1fr;
    }
  }
 
</style>

<div class="home" in:fade>
  <section>
    <h1>Projects:</h1>
    <div class="gallery">
      <div class="project">
        <h2><img src="./hacksaw.ico" alt="hacksaw logo" height="16rem">hacksaw</h2>
        <img class="image" src="./hacksaw.webp" alt="hacksaw image">
        
        <Button on:click={()=>{window.open('https://github.com/DevMarcius/Hacksaw/releases', '_blank').focus()}}>Download</Button>
      </div>
    </div>
  <!-- <h1><img src="../public/hacksaw.ico" alt="hacksaw logo" height="36rem">Hacksaw</h1>
  <img class="image" src="../public/hacksaw.webp" alt="hacksaw image"> -->
  </section>
</div>