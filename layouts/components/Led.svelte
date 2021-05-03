<script>
  import { createEventDispatcher } from "svelte/internal";
  const dispatch = createEventDispatcher();
  export let brightness = 9;
  export let selected = false;
  const toggleLED = () => {
    dispatch("toggle");
  };
  console.log("LED");
</script>

<style>
  div {
    margin: 0 6px 0 0;
    display: inline-block;
    width: 12px;
    height: 20px;
    border: rgb(212, 212, 212) solid 2px;
  }
  .selected {
    border: blue solid 2px;
  }
  .level0 {
    background-color: rgba(255, 0, 0, 0);
  }
  .level0 {
    background-color: rgba(255, 0, 0, 0);
  }
  .level0 {
    background-color: rgba(255, 0, 0, 0);
  }
  .level0 {
    background-color: rgba(255, 0, 0, 0);
  }
  .level1 {
    background-color: rgba(255, 0, 0, 0.2);
  }
  .level2 {
    background-color: rgba(255, 0, 0, 0.3);
  }
  .level3 {
    background-color: rgba(255, 0, 0, 0.4);
  }
  .level4 {
    background-color: rgba(255, 0, 0, 0.5);
  }
  .level5 {
    background-color: rgba(255, 0, 0, 0.6);
  }
  .level6 {
    background-color: rgba(255, 0, 0, 0.7);
  }
  .level7 {
    background-color: rgba(255, 0, 0, 0.8);
  }
  .level8 {
    background-color: rgba(255, 0, 0, 0.9);
  }
  .level9 {
    background-color: rgba(255, 0, 0, 1);
  }
</style>

<div class={'level' + brightness} class:selected on:click={toggleLED} />
