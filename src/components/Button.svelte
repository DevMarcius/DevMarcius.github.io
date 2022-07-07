<script>
  export let type = "default" // "primary", "info", "success", "error"
  export let style = ""
</script>

<style>
  button{
      height: 2rem;
      border:none;
      font-weight: bolder;
      border-radius: var(--urem-250);
      background-color: var(--gray-400);
      color: var(--gray-100);
  }
  button:hover{
      background-color: var(--gray-600);
      color: var(--gray-000);
      cursor:pointer
  }
  .button-primary{
      color: var(--gray-500);
      background-color: var(--gray-100);
  }
  .button-primary:hover{
      color: var(--white);
      background-color: var(--primary-dark);
  }
  .button-success{
      background-color: var(--success);
      color: var(--black);
  }
  .button-success:hover{
      background-color: var(--success-dark);
      color: var(--white);
  }
  .button-error{
      background-color: var(--error);
      color: var(--black);
  }
  .button-error:hover{
      background-color: var(--error-dark);
      color: var(--white);
  }
</style>

<button on:click
  style={style}
  class:button-primary="{type === "primary"}"
  class:button-success="{type === "success" || type === "yes"}"
  class:button-error="{type === "error" || type === "no"}">
  <slot/>
</button>