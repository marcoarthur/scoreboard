<script>
  import { fade } from 'svelte/transition';

  export let name;
  export let points;
  let showControls = false;

  const addPoint = () => (points += 1);
  const removePoint = () => (points -= 1);
  const toggleControls = () => ( showControls = !showControls);
</script>

<style>
  h2 {
    color: #204f6e;
  }
</style>

<div class="card">
  <h2>
    {name}
    <button class="btn btn=sm" on:click={toggleControls}>
      {#if showControls}-{:else}+{/if}
    </button>
  </h2>
  <h3>{points}</h3>

  {#if showControls}
    <div class="controls"  transition:fade>
      <button class="btn" on:click={addPoint}>+1</button>
      <button class="btn btn-dark" on:click={removePoint}>-1</button>
      <input type="number" bind:value="{points}" />
    </div>
  {/if}
</div>
