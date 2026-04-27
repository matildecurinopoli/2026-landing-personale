<script>
	import letterboxdDarkLogo from '$lib/assets/letterboxd-logo-v-neg-rgb.svg';
	import letterboxdLightLogo from '$lib/assets/letterboxd-logo-v-pos-rgb.svg';

	const letterboxdUrl = 'https://letterboxd.com';
</script>

<footer class="safe-area">
	<a href={letterboxdUrl} target="_blank" rel="noopener noreferrer">
		<picture>
			<source srcset={letterboxdDarkLogo} media="(prefers-color-scheme: dark)" /> /* DarkLogo per la modalità scura */
			<img src={letterboxdLightLogo} alt="Letterboxd" /> 
		</picture>
	</a>
</footer>

<style>
	footer {
		padding-block: var(--size-4);

		display: flex;
		justify-content: center;
		align-items: center;
	}

	a {
		display: inline-block; 
		line-height: 0;
	}

	img {
		height: var(--size-10);
	}
</style>