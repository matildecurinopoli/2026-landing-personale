<script>
    import Hero from '$lib/components/Hero.svelte';
    import Card from '$lib/components/Card.svelte';
    import { myFourFavorites } from '$lib/data/movies-info.js';
</script>

<Hero />

<main class="safe-area movie-grid">
    {#each myFourFavorites as film}
        <Card {...film} />
    {/each}
</main>

<style>
    .movie-grid {
        padding-block: var(--size-5);
        display: flex;
        flex-direction: column;
        gap: var(--size-4);
    }
</style>