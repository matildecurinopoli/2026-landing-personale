<script>
	import favicon from '$lib/assets/favicon.svg';

	import "$lib/styles/reset.css";
	import "$lib/styles/tokens.css";
	import "$lib/styles/base.css";

	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />

	<!-- Plus Jakarta Sans Font -->
	<link rel="preconnect" href="https://fonts.bunny.net/" />
	<link rel="stylesheet" href="https://fonts.bunny.net/css2?family=Plus+Jakarta+Sans:ital,wght@0,200..800;1,200..800&display=swap" />
	
	<!-- Inter Font -->
	<link rel="preconnect" href="https://rsms.me/" />
	<link rel="stylesheet" href="https://rsms.me/inter/inter.css" />
</svelte:head>

{@render children()}
