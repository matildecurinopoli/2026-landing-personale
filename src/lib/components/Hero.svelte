<script>
	import illustrationDark from '$lib/assets/illustration-dark.svg';
	import illustrationLight from '$lib/assets/illustration-light.svg';
</script>

<section class="safe-area hero">
	<div class="hero-text">
		<h1>
			This page features my four favorite films, inspired by the famous <a
				href="https://letterboxd.com/"
				target="_blank"
				rel="noopener noreferrer"
				class="letterboxd-link">Letterboxd</a
			>
			interview question.
		</h1>
	</div>
	<figure class="hero-figure">
		<picture>
			<source media="(prefers-color-scheme: dark)" srcset={illustrationDark} />
			<img src={illustrationLight} alt="Letterboxd microphone illustration" />
		</picture>
	</figure>
</section>

<style>
	.hero {
		display: grid;
		grid-template-columns: 1fr;
		gap: auto;
		padding-block: var(--size-9);
		
		& .hero-text {
			& h1 {
				margin: 0;

				& .letterboxd-link {
					color: var(--color-accent);
				}
			}
		}

		& .hero-figure {
			text-align: right;

			& picture {
				display: block;

				& img {
					width: 100%;
					height: auto;
					max-width: 100%;
					display: block;
				}
			}
		}
	}

	@media (min-width: 1024px) {
		.hero {
			grid-template-columns: 1fr 1fr;
            align-items: center;
		}
	}
</style>