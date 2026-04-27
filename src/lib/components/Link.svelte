<script>
	import Icon from "./Icon.svelte";

	const {
		ref,
		title = null,
		children = null,
		leadingIcon = null,
		trailingIcon = null,
	} = $props();

    let target = $derived.by (() => {
        if (ref.startsWith("https://") || ref.startsWith("http://")) {
            return "_blank"
        } else {
            return "_self"
        }
    })
</script>

<a href={ref} target={target}>
	{#if children}
		{@render children()}
	{:else}
		{#if leadingIcon}
			<Icon name={leadingIcon} />
		{/if}

		{title}

		{#if trailingIcon}
			<Icon name={trailingIcon} />
		{/if}
	{/if}
</a>

<style>
	a {
		@media screen and (prefers-color-scheme: light) {
			--color-hover: var(--hex-brand-600);
		}

		@media screen and (prefers-color-scheme: dark) {
			--color-hover: var(--hex-brand-500);
		}

        font-size: var(--font-size-h3); /*24px --> size-5*/

		position: relative;
		display: inline-flex;
		align-items: center;
		gap: var(--size-1);

		&::after {
			content: "";
			position: absolute;
			bottom: -0.1em; /* distanza tra testo e linea proporzionale alla dimensione del testo */
			left: 0;
			height: 0.05em; /* spessore della linea proporzionale alla dimensione del testo */
			width: 100%;
			background-color: var(--color-hover);
			transform: scaleX(0);
			transform-origin: left;

            will-change: transform; /* suggerisce al browser di ottimizzare per questa trasformazione. Problema che la linea appariva più sottile alla fine dell'animazione */
            backface-visibility: hidden; 

			transition: transform 300ms var(--ease-out-quart);
		}

		&:hover {
			color: var(--color-hover);

			&::after {
				transform: scaleX(1);
			}
		}
	}
</style>