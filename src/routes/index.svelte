<script>
	import Counter from '$lib/Counter.svelte';
	let questions = [
		{
			question: 'What is my name?',
			type: 'radio',
			answers: [{ name: 'Jeroen' }, { name: 'Jeppe' }]
		},
		{
			question: 'What are our names?',
			type: 'checkbox',
			answers: [{ name: 'Jeroen' }, { name: 'Jeppe' }, { name: 'Niels' }]
		},
		{
			question: 'What are our names?',
			type: 'checkbox',
			answers: [{ name: 'Jeroen' }, { name: 'Jeppe' }, { name: 'Niels' }]
		}
	];
</script>

<main>
	<h1>Hello world!</h1>

	{#each questions as question}
		<div>{question.question}</div>
		{#each question.answers as answer}
			<div>{answer.name}</div>
		{/each}
	{/each}

	<p>Visit <a href="https://svelte.dev">svelte.dev</a> to learn how to build Svelte apps.</p>
</main>

<style lang="scss">
	main {
		text-align: center;
		padding: 1em;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4rem;
		font-weight: 100;
		line-height: 1.1;
		margin: 4rem auto;
		max-width: 14rem;
	}

	p {
		max-width: 14rem;
		margin: 2rem auto;
		line-height: 1.35;
	}

	@media (min-width: 480px) {
		h1 {
			max-width: none;
		}

		p {
			max-width: none;
		}
	}
</style>
