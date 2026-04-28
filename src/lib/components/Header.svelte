<script>
	import Link from "$lib/components/Link.svelte";
</script>

<header class="safe-area">
	<Link title="My four favorites" shortTitle="My 4 faves" ref="/" />

	<nav>
		<Link
			title="@lamatu"
			ref="https://boxd.it/53T4z"
		/>
	</nav>
</header>

<style>
	header {
		padding-block: var(--size-6); /*padding verticale*/

		display: flex;
		gap: var(--size-8);
		justify-content: space-between;
		align-items: center;
	}

	nav {
		display: flex;
		gap: var(--size-6);
		align-items: center;
	}
</style>