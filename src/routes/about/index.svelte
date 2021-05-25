<script>
	import data from './items.json';
	import Slide, { DivHeight } from './Slide.svelte';
	import { onMount } from 'svelte';
	import Card from './Card.svelte';

	let sliderHeight;
	let sliderHeightMultiplier = 1.5;
	onMount(() => {
		sliderHeight = DivHeight * sliderHeightMultiplier + 'px';
		console.log(sliderHeight);
	});

	export let key;

	let slides = [];

	let slideCounter = 0;

	const nextSlide = () => {
		if (slideCounter < data.length - 1) {
			slideCounter++;
		} else {
			slideCounter = 0;
		}
		slides = [data[slideCounter]];
		key = [data[slideCounter]];
	};
	const previousSlide = () => {
		if (slideCounter === 0) {
			slideCounter = data.length;
		}
		slideCounter--;
		slides = [data[slideCounter]];
		key = [data[slideCounter]];
	};

	nextSlide();
</script>

<p>Current slide: {slideCounter}</p>
<button on:click={nextSlide}>Next slide</button>
<button on:click={previousSlide}>Previous slide</button>

<div class="slider" style="--height:{sliderHeight}">
	{#each slides as slide}
		<Slide refresh={key}>{slide.question}</Slide>
	{/each}
</div>

<div class="data">
	{#each data as slide}
		<Card>{slide.question}</Card>
	{/each}
</div>

<style>
	.data {
		border-top: 1px solid #333;
		padding-top: 2em;
		margin-top: 2em;
		opacity: 0.35;
	}
	.slider {
		display: flex;
		justify-content: center;
		overflow: visible;
		position: relative;
		height: var(--height);
	}
</style>
