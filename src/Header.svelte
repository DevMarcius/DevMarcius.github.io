<script>
  import { push } from "svelte-spa-router";
  import NavButton from "./components/NavButton.svelte";
  import {location} from 'svelte-spa-router'

  
  let navPaths = [
    {
      id: 0,
      name: "Home",
      path: "#/",
    },
    {
      id: 1,
      name: "Mod Wiki",
      path: "#/wiki/test/stuff",
    },
    {
      id: 2,
      name: "About",
      path: "#/about",
    },
  ];
  let activeTab
  
  for (let i = navPaths.length-1; i >= 0; i--) {
    if ($location == navPaths[i].path) {
      activeTab = i;
    }
  }
  
  

  function changeTab(loc) {
    push(loc.path);
    activeTab = loc.id;
  }
</script>

<nav>
  <img class="logo" src="/lightM.svg" />
  {#each navPaths as loc}
    <NavButton
      active={activeTab==loc.id}
      on:click={() => {
        changeTab(loc);
      }}>{loc.name}</NavButton
    >
  {/each}
</nav>

<style>
  nav {
    padding-inline: 1rem;
    position: fixed;
    display: flex;
    top: 0;
    width: 100%;
    background: var(--gray-500);
    height: 3rem;
  }
  .logo {
    display: block;
    height: 2.5rem;
    padding: 0.25rem;
  }
</style>
