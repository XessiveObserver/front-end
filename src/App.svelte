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
			<input type="number" bind:value="{counter}">
			{/if}
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
		width: 60%;
		padding:0px;
		margin:0px;
		background-color: antiquewhite;
		margin-right: 5px;
		display: block;
	}
	aside {
		padding:0px;
		padding:0px;
		width: 30%;
		float:left;
		background-color: azure;
	}
	section, aside, article{
		margin-top: 5px;
	}
	nav li { list-style: none;
		display: inline;
	}
	nav li a{
		margin-right: 100px;
		text-decoration: none;
		color:darkgreen;
		display:inline-block;
	}
	nav li a:hover {
		color:darkgray;
	}
	header{
		text-align: center;
		background-color: lightgreen;
		
	}
	footer{
		text-align:center;
	}
	header, footer {
		clear:both;
		font-weight: bolder;
	}
</style>