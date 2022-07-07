<script>
</script>

<style>
  button{
    text-align: start;
    position:relative;
    justify-content: start;
    height: 2rem;
    padding-left: 2rem;
    border:none;
    font-size:1rem;
    border-radius: var(--urem-250);
    background-color: transparent;
    color: var(--gray-100);
  }
  button:hover{
      background-color: transparent;
      color: var(--gray-000);
      cursor:pointer;
  }
  button:focus{
      outline:none;
  }
  button:focus-visible{
    color: var(--blue);
  }
</style>

<button on:click>
  <slot/>
</button>