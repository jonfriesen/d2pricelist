<script>
	export let value = '';
</script>

<div class="w-full">
	<label for="search" class="sr-only">Search items</label>
	<div class="relative text-gray-900 focus-within:text-gray-900">
		<div class="absolute inset-y-0 left-0 pl-3 flex items-center pointer-events-none">
			<!-- Heroicon name: solid/search -->
			<svg
				class="h-5 w-5"
				xmlns="http://www.w3.org/2000/svg"
				viewBox="0 0 20 20"
				fill="currentColor"
				aria-hidden="true"
			>
				<path
					fill-rule="evenodd"
					d="M8 4a4 4 0 100 8 4 4 0 000-8zM2 8a6 6 0 1110.89 3.476l4.817 4.817a1 1 0 01-1.414 1.414l-4.816-4.816A6 6 0 012 8z"
					clip-rule="evenodd"
				/>
			</svg>
		</div>
		<input
			id="search"
			name="search"
			bind:value
			class="block w-full pl-10 pr-3 py-2 border border-transparent rounded-md leading-5 bg-gray-400 bg-opacity-25 text-gray-700 placeholder-gray-600 focus:outline-none focus:bg-gray-200 focus:ring-0 focus:placeholder-gray-400 focus:text-gray-900 sm:text-sm"
			placeholder="Search items"
			type="search"
		/>
	</div>
</div>
