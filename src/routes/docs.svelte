<script context="module">
  import Header from "../lib/header/Header.svelte";
  
  export const prerender = true;
</script>
  
  
  <svelte:head>
    <title>Home</title>
    <meta name="description" content="Svelte demo app" />
  </svelte:head>
  
  <Header />
  <section>
    <h2>
      hello
    </h2>
  </section>
  
  <style>
    section {
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      flex: 1;
    }
  </style>
  