<script>
	import Item from './Item.svelte';
	import ItemData from '../data/items';
</script>

<div class="bg-white shadow overflow-hidden sm:rounded-md">
	<ul role="list" class="divide-y divide-gray-200">
		{#each ItemData as AnItem}
			<Item item={AnItem} />
		{/each}
	</ul>
</div>
