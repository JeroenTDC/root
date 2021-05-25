<script context="module">
	export let DivHeight;
</script>

<script>
	import { fly } from 'svelte/transition';
	export let refresh = '';

	const onload = (el) => {
		console.log(el.clientHeight);
		DivHeight = el.clientHeight;
	};
</script>

{#key refresh}
	<div use:onload in:fly={{ x: 100, duration: 500 }} out:fly={{ x: -100, duration: 500 }}>
		<slot />
	</div>
{/key}

<style>
	div {
		padding: 1em;
		margin: 1em;
		border: 1px solid #e2e2e2;
		box-shadow: 0 2px 8px rgba(0, 0, 0, 0.05);
		position: absolute;
	}
</style>
