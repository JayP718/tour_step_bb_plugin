<script>
  import { getContext } from "svelte"

  export let text
  export let pop_position
  export let title

  const { styleable } = getContext("sdk")
  const component = getContext("component")
  const uuid = Math.random()
</script>        

<div use:styleable={$component.styles}>
  <div class="sheep_step" id={uuid} data-pos={pop_position} data-text={text} data-title={title}>
    i 
    <slot/>
  </div>   
</div>


 