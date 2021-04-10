<script>
import Games from "./Games.svelte";
import Hobbies from "./Hobbies.svelte";
import Topics from "./Topics.svelte";



	let counter = 0;
	let showControls = false;

	const addCounter = () => counter += 1;
	const subtractCounter = () => counter -= 1;
	const toggleControls = () => {showControls = !showControls}
</script>

<main>
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
			</p>	
			<hr>
			<p>
				<Topics />
			</p>

			<br>
			<br>
			<hr>
			<p>
				<Games />
			</p>
			
		</article>
	</section>
		
	<aside>
		<section>
			<p>
				<Hobbies />
			</p>
			
		</section>		
	</aside>
		
	
	<footer>
		&copy; All rights reserved 2021
	</footer>
	
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

	article {
		border-radius: 8px;
		float:left;
		width: 65%;
		padding:0px;
		margin:0px;
		background-color:lightcyan;
		margin-right: 8px;
		display: block;
		margin-bottom: 8px;
	}
	aside {
		width: 30%;
		float:left;
		background-color: lightcyan;
		border-radius: 8px;
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
		margin-top: 12px;
	}
	nav li a:hover {
		color:lightseagreen;
	}
	header{
		text-align: center;
		background-color: lightgreen;
		height: 50px;
		border-radius: 8px;
		
	}
	footer{
		text-align:center;
		border-radius:8px;
		background-color: lightgreen;
		height: 30px;
	}
	nav, footer {
		clear:both;
		font-weight: bolder;
	}
	p {
		margin-left: 8px;
	}
	* {
	box-sizing: border-box;
	}
</style>