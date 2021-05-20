<script>
	let disabled = false;

	let show = false;

	let promiseMe;

	function fetchPromise() {
		promiseMe = fetch('https://celoapp.herokuapp.com/survey');
		console.log(promiseMe);
	}

	function handleClick() {
		// Now set it to the real fetch promise
		// promise = fetchUsers();
		fetchPromise();
		disabled = true;
		show = true;
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

<div class="prev-btn"><span class="fa fa-angle-up" /></div>
<div class="next-btn">Press ENTER or <span class="fa fa-angle-down">Continue</span></div>
<div class="nav-dots">
	<div class="nav-dot" data-slide="1" />
	<div class="nav-dot" data-slide="2" />
	<div class="nav-dot" data-slide="3" />
	<div class="nav-dot" data-slide="4" />
	<div class="nav-dot" data-slide="5" />
	<div class="nav-dot" data-slide="6" />
	<div class="nav-dot" data-slide="7" />
</div>

{#each questions as question}
	<div class="panel" data-slide={question.id}>
		<div class="trans-layer" id="layer-1" />
		<section class="section" id="section-1">
			<div class="section-content">
				<h1>{question.question}</h1>
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
		</section>
	</div>
{/each}
<div class="panel topLayer" data-slide="8">
	<div class="trans-layer" id="layer-8" />
	<section class="section" id="section-8">
		<div class="section-content final">
			{#if show === false}
				<img class="yaw" src="handshake.gif" />
				<h1>Almost there..</h1>
				<button class="doit" on:click={handleClick} {disabled}> Get you reward!</button>
			{/if}
			{#if show === true}
				<img class="yaw" src="handshake.gif" />
				<h1>You did it!</h1>
				<p>Use the close-icon at the top-right corner <br />to return to the HejOne+ site</p>
				<img class="arrow" src="arrow.svg" />
			{/if}
		</div>
	</section>
</div>

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
