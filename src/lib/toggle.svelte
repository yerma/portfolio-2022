<script>
  import { createEventDispatcher } from 'svelte';
  export let initialState = false;
  export let labelActive;
  
  const dispatch = createEventDispatcher();
  let active = initialState;

  function toggleActive () {
    dispatch('toggle', active)
  }

</script>
<div class="toggle">
  <label class:active>
    <input type="checkbox"
      bind:checked={active}
      on:change={toggleActive}
    />
    {#if active}
      { labelActive }
    {:else}
      <slot></slot>
    {/if}
  </label>
</div>

<style type="scss">
  .toggle {
    position: absolute;
    top: 1.2em;
    right: 1.2em;
  }
  
  label {
    padding: 4px 8px;
    background: var(--text-color);
    border-radius: 50px;
    position: relative;
    cursor: pointer;
    display: inline-flex;

    input {
      position: absolute;
      left: -9999px;
    }
  }
</style>
