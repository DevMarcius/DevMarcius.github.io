<script>
    export let active = false
</script>

<style>
    button{
        position:relative;
        height: 3rem;
        padding-inline: 1rem;
        border:none;
        font-weight: bolder;
        border-radius: var(--rounded);
        background-color: transparent;
        color: var(--gray-100);
    }
    button:hover{
        background-color: transparent;
        color: var(--gray-000);
        cursor:pointer;
    }
    .active{
        color: var(--gray-000);
        cursor:default;
    }
    button:focus{
        outline:none;
    }
    button:focus-visible::after,
    .active::after{
        content: "";
        position: absolute;
        bottom: 0.25rem;
        left: 0;
        width: calc(60%);
        transform: translate(35%,0);
        height: 0.25rem;
        background-color: var(--blue);
        border-radius: 0.3rem;
    }
    .active::after{
        background-color: var(--gray-000);
    }
</style>

<button on:click class:active="{active === true}">
    <slot/>
</button>