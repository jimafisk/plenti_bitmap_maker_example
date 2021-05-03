<script>
  import Led from "./Led.svelte";
  import { createEventDispatcher } from "svelte/internal";
  const dispatch = createEventDispatcher();
  export let intensity;
  const intensities = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9];
  const toggleLED = nr => {
    console.log("TOGGLE : ", nr);
    dispatch("newIntensity", { intensity: nr });
  };
</script>

<style>
  div {
    width: 320px;
    padding: 4px 10px 4px 10px;
    background-color: rgb(243, 241, 241);
  }
</style>

<div>
  <span>Brightness:</span>
  {#each intensities as value, i}
    {#if value === intensity}
      <Led brightness={value} selected={true} on:toggle={() => toggleLED(i)} />
    {:else}
      <Led brightness={value} selected={false} on:toggle={() => toggleLED(i)} />
    {/if}
  {/each}
  <!-- {#each intensities as value, i}
    {#if value === i}
      {intensity}
      <Led on:toggle={()=>toggleLED(i)}</Led>/>
    {/if}
  {/each} -->
  <!-- {#each intensities as brightness, i}
    {#if select.includes(i)}
      <Led {brightness} selected={true} />
    {:else}
      <Led {brightness} selected={false} />
    {/if}
  {/each} -->
</div>
