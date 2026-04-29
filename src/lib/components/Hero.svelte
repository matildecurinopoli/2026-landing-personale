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
	<figure class="hero-illustration">
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
		gap: var(--size-7);
		padding-block: var(--size-8);
		
		& .hero-text {
			& h1 {
				font-size: var(--font-size-h2);

				& .letterboxd-link {
					color: var(--color-accent);
				}
			}
		}

		& .hero-illustration {
            & picture {
                display: block;
            }
            
            & img {
                width: 100%;
                height: auto;
            }
		}
	}

    @media (min-width: 768px) {
        .hero {
            gap: var(--size-8);

            & .hero-text {
                max-width: 75dvw;

                & h1 {
                    font-size: var(--font-size-h1);
                }
            }  
        }
    }

	@media (min-width: 1024px) {
		.hero {
			grid-template-columns: 1fr 1fr;
            align-items: center;
            gap: var(--size-6);

            & .hero-text {
                max-width: none;
            }
		}
	}
</style>