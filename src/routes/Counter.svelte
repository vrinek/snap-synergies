<script>
	import { onMount } from 'svelte';
	import { Network } from 'vis-network';
	import { DataSet } from 'vis-data';
	import cards from './cards.js'
	import relations from './relations.js'

    const deck = ["Agent 13",
                  "Mantis",
                  "Quinjet",
                  "The Collector",
                  "Cable",
                  "Invisible Woman",
                  "Sentinel",
                  "Moon Girl",
                  "Omega Red",
                  "White Queen",
                  "Devil Dinosaur",
                  "Leech"]
    const myRelations = relations.filter(
        relation => deck.includes(relation.from) || deck.includes(relation.to)
    )
    const myCards = cards.filter(
        card => myRelations.map(r => r.from).includes(card.id) || myRelations.map(r => r.to).includes(card.id)
    )

    const nodes = new DataSet(myCards)
    const edges = new DataSet(myRelations)

	let container;
	const data = {
		nodes: nodes,
		edges: edges,
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
