<script>
	import { quintOut } from 'svelte/easing';
	import { fade, draw, fly } from 'svelte/transition';
	import { expand } from './custom-transitions.js';
	import { inner, outer, whole, outline } from './shape.js';
	import Card from '../components/Card.svelte';

	const items = [
    {
      id: 1,
      title: "Pirate",
      description: "Argg!!",
      imageUrl: "https://alligator.io/images/pirate.svg"
    },
    {
      id: 2,
      title: "Chef",
      description: "À la soupe!",
      imageUrl: "https://alligator.io/images/chef.svg"
    },
    {
      id: 3,
      title: "Chief",
      description: "À la soupe!",
      imageUrl: "https://alligator.io/images/chef.svg"
    },
    {
      id: 4,
      title: "Chef",
      description: "À la soupe!",
      imageUrl: "https://alligator.io/images/chef.svg"
    },
    {
      id: 5,
      title: "Chef",
      description: "À la soupe!",
      imageUrl: "https://alligator.io/images/chef.svg"
    }
  ];
</script>

<svelte:head>
	<title>About</title>
</svelte:head>

<style>
	svg {
		width: 40%;
		height: 40%;
		margin-bottom: 0;
		padding-bottom: 0;
	}

	.outline-svg {
		fill: none;
		stroke-miterlimit: 10;
		stroke: var(--gray); 
		stroke-width: 1.5;
	}

	.background-svg {
		fill: var(--gray);
	}

	.container {
		display: grid;
		grid-template-columns: repeat(3, minmax(200px))
	}
</style>

<div class="container">
	<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 158.24 184.4">
		<g id="Layer_2" data-name="Layer 2" out:fade="{{duration: 200}}">
			<g id="cleaned-up">
				<path 
					in:expand="{{duration: 1000, delay: 1400, easing: quintOut}}"
					class="background-svg"
					d="M79.68,82.72l0,0m0,0v0c28.13-5.65,53.92-20.64,77.49-44.38V37.7h0l-53.72-31a49.87,49.87,0,0,0-50,.07L5.92,34.42A10.89,10.89,0,0,0,.5,43.78L.17,102c6,6.78,36.29,37,66.39,44.93,1.59-7.73,1.86-63.62-53.41-85a1,1,0,0,1-.65-.84c-.38-3.07-1.91-16.64.3-16.47,3.39-5.77,93.87,8.48,66.26,128.77a1,1,0,0,1-1.48.66c-9.7-4.91-76.13-37.51-77.31-43.17-.09-.44-.17-1-.25-1.57l0,3.31A12.07,12.07,0,0,0,6,143.1L73.35,182a10.7,10.7,0,0,0,10.72,0l67.58-39.27a10.67,10.67,0,0,0,5.31-9.2l.21-73.31c-15.25,24.34-45.83,38-46.39,35.1,1.4,50.58-24.39,78.58-28.84,80C98.36,134,83.52,89.46,79.74,82.7l-.06,0M40.34,43.37a3.41,3.41,0,0,1-3.37.36c-4.14-1.94-16-5-22.44-3.43-1.37.33,4.24-3.77,5.43-4.52C68.37,5,85,3,134.77,34.37c1.08.67,8.44,8,3.42,6.23C123.55,35.33,77.12,18.28,40.34,43.37Z"
				/>
				<path 
					in:draw="{{duration: 2100}}"
					class="outline-svg" 
					d="M80.18,83.22l0,0m0,0v0c28.13-5.65,53.92-20.64,77.49-44.38V38.2h0L104,7.18a49.87,49.87,0,0,0-50,.07L6.42,34.92A10.89,10.89,0,0,0,1,44.28L.67,102.54c6,6.78,36.29,37,66.39,44.93,1.59-7.73,1.86-63.62-53.41-85A1,1,0,0,1,13,61.6c-.38-3.07-1.91-16.64.3-16.47,3.39-5.77,93.87,8.48,66.26,128.77a1,1,0,0,1-1.48.66C68.38,169.65,2,137.05.77,131.39c-.09-.44-.17-1-.25-1.57l0,3.31a12.07,12.07,0,0,0,6,10.47l67.32,38.87a10.7,10.7,0,0,0,10.72,0l67.58-39.27a10.67,10.67,0,0,0,5.31-9.2l.21-73.31c-15.25,24.34-45.83,38-46.39,35.1,1.4,50.58-24.39,78.58-28.84,80C98.86,134.51,84,90,80.24,83.2l-.06,0M40.84,43.87a3.41,3.41,0,0,1-3.37.36c-4.14-1.94-16-5-22.44-3.43-1.37.33,4.24-3.77,5.43-4.52C68.87,5.5,85.48,3.5,135.27,34.87c1.08.67,8.44,8,3.42,6.23C124.05,35.83,77.62,18.78,40.84,43.87Z"
				/>
				<path 
					d="M80.08,82.73s-.62,0-.28.69.66-.14.66-.14Z"
				/>
			</g>
		</g>
	</svg>
  <h2>Samuel Young</h2>
  <p>Designer | Developer | Adventurer</p>

  <section>
    {#each items as item}
      <Card {...item} />
    {/each}
  </section>
</div>

<!-- <div class="centered" out:fade="{{duration: 200}}">
	<span>
		{#each `Sam` as char, i}
			<span
				in:fade="{{delay: 1300 + i * 150, duration: 900}}"
			>{char}</span>
		{/each}
		{#each `Young` as char, i}
			<span
				in:fade="{{delay: 1300 + i * 150, duration: 900}}"
			>{char}</span>
		{/each}
	</span>
</div>

<link href="https://fonts.googleapis.com/css?family=Overpass:100" rel="stylesheet"> -->