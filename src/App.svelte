<script>
import Fruits from "./Fruits.svelte";

	let counter = 0;
	let showControls = false;

	const addCounter = () => counter += 1;
	const subtractCounter = () => counter -= 1;
	const toggleControls = () => {showControls = !showControls}
</script>
<header>
	<nav>
		<li><a href="/">Home</a></li>
		<li><a href="/">Portfolio</a></li>
		<li><a href="/">Blog</a></li>
		<li><a href="/">Contact</a></li>
	</nav>
</header>
<section>
	<article>
		
		<p>
			
			<button>{counter}</button>
			<button on:click="{toggleControls}">
				{#if !showControls}
					Show Controls
				{:else}
					Hide Controls
				{/if}
			</button>
			{#if showControls}
			<button on:click={addCounter}>+ Add</button>
			<button on:click={subtractCounter}>- Subtract</button>
			{/if}
		</p>
			
		<p>
			<input type="number" bind:value="{counter}">
		</p>
		
	</article>
</section>
	
<aside>
	<section>
		<p>
			<Fruits />
		</p>
	</section>		
</aside>
	

<footer>
	&copy; All rights reserved 2021
</footer>

<style>
	button{
		background-color: green;
		border-radius: 20px;
		color: whitesmoke;
		font-weight: bolder;
	}
	input{
		border-radius: 50px;
	}

	article {
	
		float:left;
		width: 65%;
		padding:0px;
		margin:0px;
		border: 1px solid;
	 
	}
	aside {
		padding:0px;
		padding:0px;
		border: 1px solid;
		background-color: aqua;
		width: 30%;
		float:left;
	}
	nav li { list-style: none;
		display: inline;
	}
	nav li a{
		margin-right: 100px;
		text-decoration: none;
	}
</style>