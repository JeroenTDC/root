<script>
	let disabled = false;
	let promise = Promise.resolve([]);

	async function fetchUsers() {
		const response = await self.fetch('https://api.github.com/users?per_page=5');
		//const response = await self.fetch('https://celoapp.herokuapp.com/survey');

		if (response.ok) {
			return response.json();
		} else {
			throw new Error();
		}
	}

	let promiseMe;

	function fetchPromise() {
		//promiseMe = fetch('https://ghibliapi.herokuapp.com/people');
		promiseMe = fetch('https://celoapp.herokuapp.com/survey', {
			mode: 'no-cors'
		});
		//promiseMe = fetch('https://celoapp.herokuapp.com/survey');
		disabled = true;
		console.log(promiseMe);
	}

	function handleClick() {
		// Now set it to the real fetch promise
		// promise = fetchUsers();
		fetchPromise();
		disabled = true;
	}

	let questions = [
		{
			id: 1,
			question: 'Beholder jeg mit nuværende mobilnummer i den nye One+ løsning?',
			answers: [
				'Ja - med mindre din arbejdsgiver fravælger det',
				'Nej - vi bliver nødsaget til at give dig et nyt nummer'
			]
		},
		{
			id: 2,
			question: 'Kan man godt have One+ uden mobiltelefon?',
			answers: [
				'Ja, man kan også benytte en bordtelefon',
				'Nej, da One + er et mobilt abonnement, kan man kun bruge mobiltelefonen'
			]
		},
		{
			id: 3,
			question: 'Får jeg automatisk 5G med mit mobilabonnement?',
			answers: [
				'Selvfølgelig, One+ er førdt med 5G',
				'Måske, det afhænger hvilket abonnement din virksomhed'
			]
		},
		{
			id: 4,
			question: 'Hvor mange forskellige mobilabonnementer er der i One+?',
			answers: [
				'4 - Basis, Standard, Professionel, Premium',
				'3 - Standard, Professionel og Premium',
				'2 - Professionel og Premium'
			]
		},
		{
			id: 5,
			question: 'Hvor mange datadelingskort kan man på mobilabonnementet: Mobil Premium?',
			answers: ['Op til 5 datalingskort', 'Op til 4 datadelingskort', 'Op til 3 datadelingskort']
		},
		{
			id: 6,
			question: 'Har alle abonnementerne følgende feature >fri tale, sms og mms<?',
			answers: ['Ja', 'Nej']
		},
		{
			id: 7,
			question: 'Hvad er TDC Erhverv Assist?',
			answers: [
				'En personlig sekretær fra TDC',
				'En app med mange fede features, så som viderestilling, Optag opkald'
			]
		}
	];
	console.log(questions);
</script>

<!-- Stop hitting GitHub on every source edit -->
<button on:click={handleClick} {disabled}> Load Users </button>

{#await promise}
	<p>...waiting</p>
{:then users}
	{#if users.length > 0}
		<p>You did it! {users.length}</p>
	{/if}
{:catch error}
	<p style="color: red">{error.message}</p>
{/await}

<main>
	{#each questions as question}
		<div class="question">
			<div class="question-heading">{question.question}</div>
			<ul>
				{#each question.answers as answer, idx}
					<li>
						<input type="radio" id={answer} name={question.id} />
						<label for={answer}>{answer}</label>
						<div class="radiobutton" />
					</li>
				{/each}
			</ul>
		</div>
	{/each}
</main>

<style lang="scss">
	main {
		text-align: center;
		padding: 1em;
		margin: 0 auto;
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
