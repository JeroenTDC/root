<script>
	import { fade } from 'svelte/transition';
	import CardFooter from './CardFooter.svelte';
	export let id;
	export let title;
	export let text;
	
	let hovering;
	let classHidden = "hidden";
	//let classHidden = "";
	let adjustHeight = "";

	function zUp() {
		this.style.zIndex = "2";
		console.log(this.style.zIndex);
	}

	function zDown() {
		this.style.zIndex = "1";
		console.log(this.style.zIndex);
	}
	
	function enter() {
		hovering = true;
		classHidden = "";
		adjustHeight = "height";
		console.log(hovering);
	}

	function leave() {
		hovering = false;
		classHidden = "hidden";
		//classHidden = "";
		adjustHeight = "";
		console.log(hovering);
	}
</script>

<style>
	* {box-sizing: border-box}
	.card-holder {
		box-sizing: border-box;
		position: relative;
		padding:0;
		min-width: 16em;
		flex-grow:1;
	  margin: 0.5em;
		height:12em;
	}
	.card {
		box-sizing: border-box;
		position: absolute;
		padding: 0;
		padding: 0;
		width: 100%;
		transition: height 0.2s;
	}
	.card-body {height: 12em; transition: height 0.2s; box-sizing: border-box;  border: 1px solid #ccc; }
	.card-body:hover {border-bottom: 0; box-shadow: 2px 2px 8px rgba(0,0,0,0.2); cursor: pointer;}
	
	.card-body-inner {height:12em; padding:1em;}
	.height { height: 19em; }
	p {font-size: 0.75rem;}
</style>

<div class="card-holder">
	<div class="card" on:mouseenter={enter} on:mouseleave={leave} on:mouseenter={zUp} on:mouseleave={zDown}>
		<div class="card-body {adjustHeight}">
			<div class="card-body-inner">
			<h3>
				{title}
			</h3>
				<p>
					{text}
				</p>
			</div>
		<CardFooter hidden={classHidden}/>
		</div>
		
	</div>
</div>