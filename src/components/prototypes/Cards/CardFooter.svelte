<script>
export let hidden = '';
</script>

<div class="card-footer {hidden}">
	<p>
		Opsig ledige licenser
	</p>
	<div class="buttons">
	<div class="btn btn-secondary">opsig</div>
	<div class="btn btn-primary">køb</div>
		</div>
</div>

<style>
	* {box-sizing: border-box; }
	p {width: 100%; font-size: 0.7rem;}
	.buttons {display:flex; align-items: flex-start; justify-content: space-between; }
	.card-footer {border-bottom:1px solid #ccc;  height: 7em; transition: opacity 0.2s, height 0.2s, padding 0.2s;box-sizing: border-box; background-color: rgba(0,0,0,0.1); background-color:white; padding: 1em; box-sizing: border-box;}
.hidden { opacity: 0; height: 0em; padding-top:0; padding-bottom:0; }
	.btn {font-size: 0.9rem; text-transform: capitalize; padding: 0.5em 1em; display:block; border: 1px solid #999; border-radius: 3px; font-weight: 600; margin-bottom: 0.5em}
	.btn-primary {background-color: #266BAF; color: white; border: 0;}
	.btn-secondary { background-color: white; }
</style>