<script>
	import Counter from './Counter.svelte';
</script>

<svelte:head>
	<title>SNAP synergies</title>
	<meta name="description" content="Svelte demo app" />
</svelte:head>

<section>
	<Counter />
</section>

<style>
	section {
		display: flex;
		position: relative;
		flex: 1;
	}
</style>
