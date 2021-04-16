<script>
    let counter = 0;
	let showControls = false;

	const addCounter = () => counter += 1;
	const subtractCounter = () => counter -= 1;
	const toggleControls = () => {showControls = !showControls}
</script>
<main>
    <button>{counter}</button>
	<button on:click="{toggleControls}" class="toggle">
		{#if !showControls}
			Show
		{:else}
			Hide 
		{/if}
		</button>
		{#if showControls}
			<button on:click={addCounter}>+ Add</button>
			<button on:click={subtractCounter}>- Subtract</button>
			<input type="number" bind:value="{counter}">
		{/if}
</main>


<style>
    .toggle {
		float: right;
		margin-right: 8px;
	}
	main {
		background-color: azure;
		border-radius: 8px;
	}
	button{
		background-color: lightgreen;
		border-radius: 20px;
		color: darkgreen;
		font-weight: bolder;
	}
	input{
		border-radius: 50px;
	}
</style>