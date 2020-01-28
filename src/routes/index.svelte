<script>
  import { onMount } from 'svelte';

  onMount(() => {
    if (window.netlifyIdentity) {
      window.netlifyIdentity.on("init", user => {
        if (!user) {
          window.netlifyIdentity.on("login", () => {
            document.location.href = "/admin/";
          });
        }
      });
    }
  });
</script>

<script>
	import { fade, draw, fly } from 'svelte/transition';
</script>

<style>
	h1, figure, p {
		text-align: center;
		margin: 0 auto;
	}

	h1 {
		font-size: 2.8em;
		text-transform: uppercase;
		font-weight: 700;
		margin: 0 0 0.5em 0;
	}

	figure {
		margin: 0 0 1em 0;
	}

	img {
		width: 100%;
		max-width: 400px;
		margin: 0 0 1em 0;
	}

	p {
		margin: 1em auto;
	}

	.centered {
		display: grid;
		grid-template-columns: repeat(9, 1fr);
		justify-content: center;
		align-content: center;
		font-size: 7em;
		/* position: absolute;
		left: 50%;
		top: 50%; */
		/* transform: translate(-50%,-50%); */
		font-family: 'Bebas Neue', 'Overpass';
		letter-spacing: 0.12em;
		color: #676778;
		font-weight: 300;
	}

	.centered span {
		will-change: filter;
	}

	@media (min-width: 480px) {
		h1 {
			font-size: 4em;
		}
	}
</style>

<svelte:head>
	<title>Sapper project template</title>
	<script src="https://identity.netlify.com/v1/netlify-identity-widget.js"></script>
</svelte:head>

<div class="centered" out:fly="{{y: -20, duration: 800}}">
	{#each 'SAM YOUNG' as char, i}
		<span
			in:fade="{{delay: 1000 + i * 150, duration: 800}}"
		>{char}</span>
	{/each}
</div>

<link href="https://fonts.googleapis.com/css?family=Overpass:100" rel="stylesheet">

<!-- <h1>Great success!</h1>

<figure>
	<img alt='Borat' src='great-success.png'>
	<figcaption>HIGH FIVE!</figcaption>
</figure>

<p>Try editing this file (src/routes/index.svelte) to test live reloading.</p> -->
