<script>
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
		<ul>
			{#each question.answers as answer}
				<li>
					<input type="radio" id="fast" name="selector" />
					<label for="fast">{answer.name}</label>
					<div class="radiobutton" />
				</li>
			{/each}
		</ul>
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
		color: rgba(0, 0, 0, 0.8);
		text-transform: uppercase;
		font-size: 2.5rem;
		font-weight: 100;
		line-height: 1.1;
		margin: 2rem auto;
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
