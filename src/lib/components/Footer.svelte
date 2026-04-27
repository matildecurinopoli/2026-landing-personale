<script>
	import letterboxd from "$lib/assets/letterboxd-logo-v-neg-rgb.svg";
</script>

<footer class="safe-area">
	<img src={letterboxd} alt="Letterboxd" />
</footer>

<style>
	footer {
		padding-block: var(--size-4);

		display: flex;
		justify-content: center;
		align-items: center;
	}

	img {
		height: var(--size-4);
	}
</style>