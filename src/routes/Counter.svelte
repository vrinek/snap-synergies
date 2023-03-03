<script>
	import { onMount } from 'svelte';
	import { Network } from 'vis-network';
	import { DataSet } from 'vis-data';
	import cards from './cards.js'
	import relations from './relations.js'

	let container;
	const data = {
		nodes: new DataSet(cards),
		edges: new DataSet(relations),
	};
	const options = {};

	onMount(() => {
		new Network(container, data, options);
	});
</script>

<div bind:this={container} />

<style>
	div {
		border: 1px solid gray;
		position: absolute;
		top: 0;
		bottom: 0;
		left: 0;
		right: 0;
	}
</style>
