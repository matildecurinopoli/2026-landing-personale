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

		display: inline-flex;
		align-items: center;
		gap: var(--space-1);

		&:hover {
			color: var(--color-hover);
		}
	}
</style>