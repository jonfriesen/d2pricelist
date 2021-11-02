<script>
	export let item = {};

	const getRarityColor = (rarity) => {
		switch (rarity.toLowerCase()) {
			case 'unique':
			case 'runeword':
				return 'text-yellow-400';
			case 'set':
				return 'text-green-500';
			case 'crafted':
				return 'text-yellow-600';
			case 'magic':
				return 'text-blue-700';
			case 'rare':
				return 'text-yellow-500';
			case 'normal':
				return 'text-gray-800';
			case 'slotted':
			case 'ethereal':
				return 'text-gray-400';
			default:
				return 'text-gray-800';
		}
	};

	const getValueString = (valueObj) => {
		const { high, low } = valueObj;
		if (high === low) {
			return high;
		}

		return `${high}-${low}`;
	};

	const getItemEmoji = (type) => {
		switch (type) {
			case 'head':
				return '👑';
			case 'chest':
				return '🧥';
			case 'feet':
				return '🥾';
			case 'hands':
				return '🧤';
			case 'waist':
				return '🧥';
			case 'ring':
				return '💍';
			case 'weapon':
				return '🗡';
			case 'shield':
				return '🛡';
			default:
				return '👽';
		}
	};
</script>

<li>
	<div class="px-4 pt-4 sm:px-6">
		<table class="min-w-full md:table-fixed">
			<thead>
				<tr>
					<td class="md:w-1/2">
						<div class=" text-sm leading-5 font-medium text-gray-900">
							{item.name}
						</div>
					</td>
					<td class="md:w-1/4"
						><div class="flex justify-end">
							<div class="text-sm leading-5 font-medium text-gray-500">Classic</div>
						</div></td
					>
					<td class="md:w-1/4"
						><div class="flex justify-end">
							<div class="text-sm leading-5 font-medium text-gray-500">Ressurected</div>
						</div></td
					>
				</tr>
			</thead>
			<tbody>
				<tr>
					<td class="">
						<div class="mt-1 flex items-center text-sm leading-5 {getRarityColor(item.rarity)}">
							<span class="mr-1">{getItemEmoji(item.type)}</span>
							<span class="ml-1">{item.sub_type}</span>
						</div>
					</td>
					<td>
						<div
							class="mt-1 flex justify-end items-center text-sm leading-5 {getRarityColor(
								item.rarity
							)}"
						>
							{#if !item.value.classic.unknown}
								<span class="text-yellow-400">{getValueString(item.value.classic)}</span>
							{:else}
								<span>
									<svg
										xmlns="http://www.w3.org/2000/svg"
										class="h-5 w-5 text-gray-300"
										viewBox="0 0 20 20"
										fill="currentColor"
									>
										<path
											fill-rule="evenodd"
											d="M18 10a8 8 0 11-16 0 8 8 0 0116 0zm-8-3a1 1 0 00-.867.5 1 1 0 11-1.731-1A3 3 0 0113 8a3.001 3.001 0 01-2 2.83V11a1 1 0 11-2 0v-1a1 1 0 011-1 1 1 0 100-2zm0 8a1 1 0 100-2 1 1 0 000 2z"
											clip-rule="evenodd"
										/>
									</svg>
								</span>
							{/if}
						</div>
					</td>
					<td>
						<div class="flex flex-col">
							<div
								class="mt-1 flex justify-end items-center text-sm leading-5 {getRarityColor(
									item.rarity
								)}"
							>
								{#if !item.value.resurrected.unknown}
									<span class="text-green-400">{getValueString(item.value.resurrected)}</span>
								{:else}
									<span>
										<svg
											xmlns="http://www.w3.org/2000/svg"
											class="h-5 w-5 text-gray-300"
											viewBox="0 0 20 20"
											fill="currentColor"
										>
											<path
												fill-rule="evenodd"
												d="M18 10a8 8 0 11-16 0 8 8 0 0116 0zm-8-3a1 1 0 00-.867.5 1 1 0 11-1.731-1A3 3 0 0113 8a3.001 3.001 0 01-2 2.83V11a1 1 0 11-2 0v-1a1 1 0 011-1 1 1 0 100-2zm0 8a1 1 0 100-2 1 1 0 000 2z"
												clip-rule="evenodd"
											/>
										</svg>
									</span>
								{/if}
							</div>
						</div>
					</td>
				</tr>
			</tbody>
		</table>
	</div>
	<div class="px-4 py-4 sm:px-6">
		<div class="pt-2 border-t border-gray-100 text-sm leading-5 font-medium text-gray-500">
			Desired
		</div>
		<div class="">
			<table class="min-w-full md:table-fixed">
				<tbody>
					{#each item.desired as desired, i}
						<tr class:bg-white={i & (2 == 0)} class:bg-gray-50={i & (2 != 0)}>
							<td class="md:w-1/2 text-sm leading-5 font-medium text-gray-500">
								<div class="ml-4 flex flex-col md:flex-row">
									{#each desired.traits as trait, x}
										<span
											>{trait}{#if x != desired.traits.length - 1},&nbsp;{/if}</span
										>
									{/each}
								</div>
							</td>
							<td
								class="md:w-1/4 text-sm leading-5 font-medium text-gray-500 whitespace-nowrap align-top"
							>
								<div class="flex justify-end">
									{#if !desired.value.classic.unknown}
										<span class="text-yellow-400">{getValueString(desired.value.classic)}</span>
									{:else}
										<span>
											<svg
												xmlns="http://www.w3.org/2000/svg"
												class="h-5 w-5 text-gray-300"
												viewBox="0 0 20 20"
												fill="currentColor"
											>
												<path
													fill-rule="evenodd"
													d="M18 10a8 8 0 11-16 0 8 8 0 0116 0zm-8-3a1 1 0 00-.867.5 1 1 0 11-1.731-1A3 3 0 0113 8a3.001 3.001 0 01-2 2.83V11a1 1 0 11-2 0v-1a1 1 0 011-1 1 1 0 100-2zm0 8a1 1 0 100-2 1 1 0 000 2z"
													clip-rule="evenodd"
												/>
											</svg>
										</span>
									{/if}
								</div>
							</td>
							<td
								class="md:w-1/4 text-sm leading-5 font-medium text-gray-500 whitespace-nowrap align-top"
							>
								<div class="flex justify-end ">
									{#if !desired.value.resurrected.unknown}
										<span class="text-green-400">{getValueString(desired.value.resurrected)}</span>
									{:else}
										<span>
											<svg
												xmlns="http://www.w3.org/2000/svg"
												class="h-5 w-5 text-gray-300"
												viewBox="0 0 20 20"
												fill="currentColor"
											>
												<path
													fill-rule="evenodd"
													d="M18 10a8 8 0 11-16 0 8 8 0 0116 0zm-8-3a1 1 0 00-.867.5 1 1 0 11-1.731-1A3 3 0 0113 8a3.001 3.001 0 01-2 2.83V11a1 1 0 11-2 0v-1a1 1 0 011-1 1 1 0 100-2zm0 8a1 1 0 100-2 1 1 0 000 2z"
													clip-rule="evenodd"
												/>
											</svg>
										</span>
									{/if}
								</div>
							</td>
						</tr>
					{/each}
				</tbody>
			</table>
		</div>
	</div>
</li>
