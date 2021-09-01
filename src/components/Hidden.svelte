<script>
  import { createEventDispatcher } from 'svelte';

  let shown = false;

  let dispatch = createEventDispatcher();

  export function show() {
      shown = !shown;
      dispatch('show', shown);
  }
</script>

<svelte:options accessors={true}/>

<button on:click={show}>Reset</button>

{#if shown}
  <slot/>
{/if}


<style>
  button{
    padding: 10px;
    color: #ff3e00;
  }
</style>
