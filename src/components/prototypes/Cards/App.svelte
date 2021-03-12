<script>
	import Card from './Card.svelte';
	
	let cardData = [
		{ id: '2', title: 'Unity Receptionist', text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Quisque sagittis augue id tincidunt convallis. Vivamus bibendum vel augue ut rutrum. Aliquam fermentum dignissim massa sed auctor.Lorem ipsum dolor sit amet, consectetur adipiscing elit. Quisque sagittis augue id tincidunt convallis.' },
		{ id: '3', title: 'Unity Receptionist', text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Quisque sagittis augue id tincidunt convallis. Vivamus bibendum vel augue ut rutrum. Aliquam fermentum dignissim massa sed auctor.Lorem ipsum dolor sit amet, consectetur adipiscing elit. Quisque sagittis augue id tincidunt convallis.' },
		{ id: '4', title: 'Unity Receptionist', text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Quisque sagittis augue id tincidunt convallis. Vivamus bibendum vel augue ut rutrum. Aliquam fermentum dignissim massa sed auctor.Lorem ipsum dolor sit amet, consectetur adipiscing elit. Quisque sagittis augue id tincidunt convallis.' },
		{ id: '5', title: 'Unity Receptionist', text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Quisque sagittis augue id tincidunt convallis. Vivamus bibendum vel augue ut rutrum. Aliquam fermentum dignissim massa sed auctor.Lorem ipsum dolor sit amet, consectetur adipiscing elit. Quisque sagittis augue id tincidunt convallis.' },
		{ id: '6', title: 'Unity Receptionist', text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Quisque sagittis augue id tincidunt convallis. Vivamus bibendum vel augue ut rutrum. Aliquam fermentum dignissim massa sed auctor.Lorem ipsum dolor sit amet, consectetur adipiscing elit. Quisque sagittis augue id tincidunt convallis.' },
		{ id: '7', title: 'Unity Receptionist', text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Quisque sagittis augue id tincidunt convallis. Vivamus bibendum vel augue ut rutrum. Aliquam fermentum dignissim massa sed auctor.Lorem ipsum dolor sit amet, consectetur adipiscing elit. Quisque sagittis augue id tincidunt convallis.' },
		{ id: '8', title: 'Unity Receptionist', text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Quisque sagittis augue id tincidunt convallis. Vivamus bibendum vel augue ut rutrum. Aliquam fermentum dignissim massa sed auctor.Lorem ipsum dolor sit amet, consectetur adipiscing elit. Quisque sagittis augue id tincidunt convallis.' },
		{ id: '9', title: 'Unity Receptionist', text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Quisque sagittis augue id tincidunt convallis. Vivamus bibendum vel augue ut rutrum. Aliquam fermentum dignissim massa sed auctor.Lorem ipsum dolor sit amet, consectetur adipiscing elit. Quisque sagittis augue id tincidunt convallis.' },
		{ id: '10', title: 'Unity Receptionist', text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Quisque sagittis augue id tincidunt convallis. Vivamus bibendum vel augue ut rutrum. Aliquam fermentum dignissim massa sed auctor.Lorem ipsum dolor sit amet, consectetur adipiscing elit. Quisque sagittis augue id tincidunt convallis.' },
		{ id: '11', title: 'Unity Receptionist', text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Quisque sagittis augue id tincidunt convallis. Vivamus bibendum vel augue ut rutrum. Aliquam fermentum dignissim massa sed auctor.Lorem ipsum dolor sit amet, consectetur adipiscing elit. Quisque sagittis augue id tincidunt convallis.' },
		{ id: '12', title: 'Unity Receptionist', text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Quisque sagittis augue id tincidunt convallis. Vivamus bibendum vel augue ut rutrum. Aliquam fermentum dignissim massa sed auctor.Lorem ipsum dolor sit amet, consectetur adipiscing elit. Quisque sagittis augue id tincidunt convallis.' },
	];
</script>

<div class="cards">
{#each cardData as { id, title, text }, i}
		<Card {id} {title} {text}/>
	{/each}
</div>

<style>
	.cards{
		padding:0;
		margin: 0;
		display: flex;
		flex-wrap: wrap;
		align-items: flex-start;
		justify-content: start;
	}
</style>