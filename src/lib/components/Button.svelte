<script>
	import Icon from "./Icon.svelte";

	const {
		variant = "primary",
		href = null,
		leadingIcon = null,
		trailingIcon = null,
		children = null,
	} = $props();

	let target = $derived.by(() => {
		if (href && (href.startsWith("https://") || href.startsWith("http://"))) {
			return "_blank";
		} else {
			return "_self";
		}
	});
</script>

{#if href}
	<a {href} {target} class="btn btn--{variant}">
		{#if leadingIcon}
			<Icon name={leadingIcon} />
		{/if}
		{#if children}
			{@render children()}
		{/if}
		{#if trailingIcon}
			<Icon name={trailingIcon} />
		{/if}
	</a>
{:else}
	<button type="button" class="btn btn--{variant}">
		{#if leadingIcon}
			<Icon name={leadingIcon} />
		{/if}
		{#if children}
			{@render children()}
		{/if}
		{#if trailingIcon}
			<Icon name={trailingIcon} />
		{/if}
	</button>
{/if}

<style>
	.btn {
		display: inline-flex;
		align-items: center;
		justify-content: center;
		gap: var(--size-2);
		border-radius: var(--size-999);
		font-weight: 400;
		border: none;
		cursor: pointer;
		transition: all 300ms var(--ease-out-quart);
		padding-block: var(--size-4);
		padding-inline: var(--size-4);
		font-size: var(--font-size-h4);

		&.btn--primary {
			background-color: var(--color-accent);
			color: var(--color-ink-inverted);
		}

		&.btn--secondary {
			background-color: var(--color-secondary-button--default);
			color: var(--color-accent);
			border: var(--size-13) solid var(--color-accent);
		}
	}

	@media (min-width: 768px) {
		.btn {
			padding-block: var(--size-3);
			padding-inline: var(--size-4);
			font-size: var(--font-size-h2);
		}
	}

	@media (min-width: 1024px) {
		.btn {
			padding-block: var(--size-2);
			padding-inline: var(--size-3);
			font-size: var(--font-size-h2);
		}
	}

	@media (min-width: 1024px) and (hover: hover) {
		.btn--primary:hover {
			background-color: var(--color-primary-button--hover);
		}

		.btn--secondary:hover {
			background-color: var(--color-secondary-button--hover);
			color: var(--color-ink-inverted);
            border: var(--size-13) solid var(--color-secondary-button--hover);
		}
	}
</style>