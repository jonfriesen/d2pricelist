<script>
	import Item from './Item.svelte';

	export let data = [];
</script>

<div class="bg-white shadow overflow-hidden sm:rounded-md">
	<ul role="list" class="divide-y divide-gray-200">
		{#each data as item}
			<Item {item} />
		{/each}
	</ul>
</div>
