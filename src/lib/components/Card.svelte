<script>
    import Button from "./Button.svelte";

    const {
        movieName,
        year,
        director,
        genre,
        country,
        locandina,
        letterboxdMovieUrl,
        trailerUrl,
    } = $props();
</script>

<article class="card">
    <div class="card__image-container">
        <img src={locandina} alt={`Poster of ${movieName}`} />
    </div>

    <div class="card__content">
        <div class="card__title">
            <span class="movie-name">{movieName}</span>
            <span class="separator">/</span>
            <span class="year">{year}</span>
        </div>

        <div class="card__metadata">
            <div class="metadata-row">
                <span class="label">Directed by</span>
                <span class="value">{director}</span>
            </div>
            <div class="metadata-row">
                <span class="label">Genre</span>
                <span class="value">{genre}</span>
            </div>
            <div class="metadata-row">
                <span class="label">Country</span>
                <span class="value">{country}</span>
            </div>
        </div>

        <div class="card__buttons">
            <Button variant="primary" href={letterboxdMovieUrl}>See on Letterboxd</Button>
            <Button variant="secondary" leadingIcon="play" href={trailerUrl}>Watch trailer</Button>
        </div>
    </div>
</article>

<style>
    .card {
        background-color: var(--color-surface);
        border-radius: var(--size-5);
        padding: var(--size-3);
        display: flex;
        flex-direction: column;
        gap: var(--size-2); /* Gap img e contenuto testuale */

        & .card__image-container {
            border-radius: var(--size-3);
            overflow: hidden;
            height: 30.5rem;
            aspect-ratio: 3 / 4.5;
            flex-shrink: 0;

            & img {
                width: 100%;
                height: 100%;
                object-fit: cover;
                display: block;
                transition: transform 300ms var(--ease-out-quart);
            }
        }

        & .card__content {
            display: flex;
            flex-direction: column;
            flex: 1;

            & .card__title {
                font-size: var(--font-size-h2);
                display: flex;
                justify-content: flex-end;
                gap: var(--size-1);
                margin-bottom: var(--size-4); /* Gap di size-4 sotto il titolo */

                & .movie-name {
                    color: var(--color-ink);
                }

                & .separator,
                & .year {
                    color: var(--color-ink-secondary);
                }
            }

            & .card__metadata {
                display: flex;
                flex-direction: column;
                gap: var(--size-2);
                margin-bottom: var(--size-5); /* Gap di size-5 tra info e bottoni */

                & .metadata-row {
                    display: flex;
                    justify-content: flex-end; /* info ancorate a destra */

                    & .label {
                        display: none; /* label nascoste */
                    }

                    & .value {
                        font-size: var(--font-size-h4);
                        color: var(--color-ink);
                    }
                }
            }

            & .card__buttons {
                display: flex;
                flex-direction: column; /* bottoni uno sotto l'altro */
                gap: var(--size-3);
                width: 100%; /* Forza la larghezza piena */
            }
        }
    }

    /* TABLET */
    @media (min-width: 768px) {
        .card {
            flex-direction: row;
            height: 23rem;
            max-width: 69rem;
            gap: var(--size-5); /* Gap tra immagine e contenuto testuale */

            & .card__image-container {
                height: 100%;
            }

            & .card__content {
                & .card__title {
                    order: 3;
                    font-size: var(--font-size-h1);
                    margin-bottom: 0;
                    margin-top: auto; /* Titolo ancorato in basso */
                }

                & .card__metadata {
                    order: 1;
                    margin-bottom: 0;

                    & .metadata-row {
                        justify-content: space-between; /* Label a sx, value a dx */
                        
                        & .label {
                            display: block; /* Label visibili solo su tablet/desktop */
                            font-size: var(--font-size-h3);
                            color: var(--color-ink-secondary);
                        }

                        & .value {
                            font-size: var(--font-size-h3);
                        }
                    }
                }

                & .card__buttons {
                    order: 2;
                    margin-top: var(--size-8);             
                    align-self: flex-end; /* Sposta l'intero blocco a destra */                                       
                    width: max-content; /* Rende il contenitore del bottone largo quanto il bottone più lungo */                                       
                    align-items: stretch; /* Forza tutti i bottoni ad allargarsi quanto il contenitore */                  
                }
            }
        }
    }

    /* DESKTOP */
    @media (min-width: 1024px) {
        .card {
            height: 29.5rem;
            max-width: 100rem;
        }
    }

    @media (min-width: 1024px) and (hover: hover) {
        .card:hover .card__image-container img {
            transform: scale(1.05);
        }
    }
</style>