<script>
	export let title;
  import BitmapMaker from '../components/BitmapMaker.svelte'; 
</script>

<h1>{title}</h1>

<BitmapMaker />

<style>
	h1 {
		font-family: Helvetica, sans-serif;
	}
</style>
