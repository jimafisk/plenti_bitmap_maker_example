<script>
  export let list = [];
</script>

<style>
  /* your styles go here */
</style>

<h1>List of Saved Images</h1>
<!-- markup (zero or more items) goes here -->
<ul>
  {#each list as item}
    <!-- content here -->
  {:else}
    <li>No images saved as yet</li>
  {/each}

</ul>
