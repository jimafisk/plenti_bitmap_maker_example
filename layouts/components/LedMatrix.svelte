<script>
  import { createEventDispatcher } from "svelte/internal";
  const dispatch = createEventDispatcher();
  export let matrix;

  import Led from "./Led.svelte";
  const toggleLed = (i, j) => {
    dispatch("selectLED", { row: i, col: j });
  };
</script>

<style>
  /* your styles go here */
</style>

<h1>LED Matrix</h1>
{#each matrix as row, i}
  <div>
    {#each row as col, j}
      <Led brightness={matrix[i][j]} on:toggle={() => toggleLed(i, j)} />
    {/each}
  </div>
{/each}
