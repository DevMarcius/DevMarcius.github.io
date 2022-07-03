<script>
  import Router from "svelte-spa-router";
  // @ts-ignore
  import Home from "./routes/Home.svelte";
  import Wiki from "./routes/Wiki.svelte";
  import NotFound from "./routes/NotFound.svelte";
  import Header from "./Header.svelte";
  

  let routes = {
    "/": Home,
    "/wiki/:topic": Wiki,
    "/wiki/:topic/:subtopic": Wiki,

    "*": NotFound,
  };
</script>

<style>
  main{
    overflow:auto;
    flex:1;
    margin-top:3rem;
  }
</style>


<Header/>
<main>
  <Router {routes} />
</main>
