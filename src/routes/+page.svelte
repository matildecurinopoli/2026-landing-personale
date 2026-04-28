<script>
	import Hero from '$lib/components/Hero.svelte';
    import Button from '$lib/components/Button.svelte';
</script>

<Hero />

<div style="padding: var(--size-10) var(--size-11); display: flex; gap: var(--size-4); flex-wrap: wrap;">
	
	<Button 
		variant="primary" 
		href="https://letterboxd.com/" 
		trailingIcon="arrow-right"
	>
		See on Letterboxd
	</Button>

	<Button 
		variant="secondary" 
		leadingIcon="play"
	>
		Watch trailer
	</Button>

</div>