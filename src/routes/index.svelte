<script>
	import SearchBar from '$lib/SearchBar.svelte';
	import ItemList from '$lib/ItemList.svelte';
</script>

<!--
  This example requires Tailwind CSS v2.0+ 
  
  This example requires some changes to your config:
  
  ```
  // tailwind.config.js
  module.exports = {
    // ...
    plugins: [
      // ...
      require('@tailwindcss/forms'),
    ],
  }
  ```
-->
<!-- Background color split screen for large screens -->
<div class="fixed top-0 left-0 w-1/2 h-full bg-white" aria-hidden="true" />
<div class="fixed top-0 right-0 w-1/2 h-full bg-gray-50" aria-hidden="true" />
<div class="relative min-h-screen flex flex-col">
	<!-- Navbar -->
	<nav class="flex-shrink-0 bg-indigo-600">
		<div class="max-w-7xl mx-auto px-2 sm:px-4 lg:px-8">
			<div class="relative flex items-center justify-between h-16">
				<!-- Logo section -->
				<div class="flex items-center px-2 lg:px-0 xl:w-64">
					<div class="flex-shrink-0">
						<img
							class="h-8 w-auto"
							src="https://tailwindui.com/img/logos/workflow-mark-indigo-300.svg"
							alt="Workflow"
						/>
					</div>
				</div>
				<div class="flex lg:hidden">
					<!-- Mobile menu button -->
					<a
						href="https://github.com/jonfriesen/d2pricelist"
						class="bg-indigo-600 inline-flex items-center justify-center p-2 rounded-md text-indigo-400 hover:text-white hover:bg-indigo-600 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-offset-indigo-600 focus:ring-white"
						aria-controls="mobile-menu"
						aria-expanded="false"
						target="_blank"
					>
						<img class="h-8 w-8 rounded-full" src="octocat.png" alt="" />
					</a>
				</div>
				<!-- Links section -->
				<div class="hidden lg:block lg:w-80">
					<div class="flex items-center justify-end">
						<div class="flex">
							<a
								href="#"
								class="px-3 py-2 rounded-md text-sm font-medium text-indigo-200 hover:text-white"
								>About</a
							>
						</div>
						<div class="ml-4 relative flex-shrink-0">
							<div>
								<a
									href="https://github.com/jonfriesen/d2pricelist"
									class="flex text-sm rounded-full text-white focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-offset-indigo-700 focus:ring-white"
									id="user-menu-button"
									aria-expanded="false"
									aria-haspopup="true"
									target="_blank"
								>
									<img class="h-8 w-8 rounded-full" src="octocat.png" alt="" />
								</a>
							</div>
						</div>
					</div>
				</div>
			</div>
		</div>

		<!-- Mobile menu, show/hide based on menu state. -->
		<div class="lg:hidden" id="mobile-menu">
			<div class="px-2 pt-2 pb-3">
				<a
					href="#"
					class="block px-3 py-2 rounded-md text-base font-medium text-white bg-indigo-800">About</a
				>
			</div>
		</div>
	</nav>

	<!-- 3 column wrapper -->
	<div class="flex-grow w-full max-w-7xl mx-auto xl:px-8 lg:flex">
		<!-- Left sidebar & main wrapper -->
		<div class="flex-1 min-w-0 bg-white xl:flex">
			<div
				class="border-b border-gray-200 xl:border-b-0 xl:flex-shrink-0 xl:w-64 xl:border-r xl:border-gray-200 bg-white"
			>
				<div class="h-full pl-4 pr-6 py-6 sm:pl-6 lg:pl-8 xl:pl-0">
					<!-- Start left column area -->
					<SearchBar />
					<!-- End left column area -->
				</div>
			</div>

			<div class="bg-white lg:min-w-0 lg:flex-1">
				<div class="h-full py-6 px-4 sm:px-6 lg:px-8">
					<!-- Start main area-->
					<ItemList />
					<!-- End main area -->
				</div>
			</div>
		</div>

		<div
			class="bg-gray-50 pr-4 sm:pr-6 lg:pr-8 lg:flex-shrink-0 lg:border-l lg:border-gray-200 xl:pr-0"
		>
			<div class="h-full pl-6 py-6 lg:w-80">
				<!-- Start right column area -->
				<div class="h-full relative" style="min-height: 16rem;">
					<div class="absolute inset-0 border-2 border-gray-200 border-dashed rounded-lg" />
				</div>
				<!-- End right column area -->
			</div>
		</div>
	</div>
</div>
