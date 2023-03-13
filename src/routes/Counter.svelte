<script>
	import { onMount } from 'svelte';
	import { Network } from 'vis-network';
	import { DataSet } from 'vis-data';
	import cards from './cards.js'
	import relations from './relations.js'

    // TODO make this a prop for this component, then make an input component for it
    const deckBase64 = "eyJDYXJkcyI6W3siQ2FyZERlZklkIjoiTW9vbkdpcmwifSx7IkNhcmREZWZJZCI6Ik1hbnRpcyJ9LHsiQ2FyZERlZklkIjoiV2hpdGVRdWVlbiJ9LHsiQ2FyZERlZklkIjoiQ2FibGUifSx7IkNhcmREZWZJZCI6IkRldmlsRGlub3NhdXIifSx7IkNhcmREZWZJZCI6IkFnZW50MTMifSx7IkNhcmREZWZJZCI6IlRoZUNvbGxlY3RvciJ9LHsiQ2FyZERlZklkIjoiU2VudGluZWwifSx7IkNhcmREZWZJZCI6Ik9tZWdhUmVkIn0seyJDYXJkRGVmSWQiOiJRdWluamV0In0seyJDYXJkRGVmSWQiOiJJbnZpc2libGVXb21hbiJ9LHsiQ2FyZERlZklkIjoiTGVlY2gifV19"

    const deckObj = JSON.parse(atob(deckBase64))
    const deckCardIds = deckObj.Cards.map(c => c.CardDefId)
    const deckCards = deckCardIds.map(
        id => cards.find(c => c.id.split(" ").join("") == id)
    )

    const deck = deckCards.map(c => c.id)

    const myRelations = relations.filter(
        relation => deck.includes(relation.from) || deck.includes(relation.to)
    )

    const myCards = cards.filter(
        card => myRelations.map(r => r.from).includes(card.id) || myRelations.map(r => r.to).includes(card.id)
    ).map(card => {
        return {...card, opacity: (deck.includes(card.id) ? 1 : 0.5)}
    })

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
