<script>
  import { getContext } from "svelte";
  export let ranking;
   
  $: error = ranking < 1 ? "Please assign a ranking greater than 0" : false;

  //Shepherd walk-through step picks up attribute once the complete Dom has loaded
  const { styleable} = getContext("sdk");
  const component = getContext("component");

</script>
    
<div use:styleable={$component.styles}>
  {#if error}
    <div class="error">{error}</div>
  {:else}
    <div id={$component.id}>
      <slot />
    </div>
  {/if}
</div>
     
<style>
  .error {
    color: white;
    font-size: var(--spectrum-global-dimension-font-size-75);
    margin-top: var(--spectrum-global-dimension-size-75);
    background: red;
  } 
</style> 
    