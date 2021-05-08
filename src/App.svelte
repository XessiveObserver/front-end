<script>
import Articles from "./Articles.svelte";
import Counter from "./Counter.svelte";
import Games from "./Games.svelte";
import Hobbies from "./Hobbies.svelte";
import News from "./News.svelte";
import Topics from "./Topics.svelte";



	
</script>

<div class="wrapper">
	<header>
		<nav>
			<ul>
					<li><a href="/">Home</a></li>
					<li><a href="/">Portfolio</a></li>
					<li><a href="/">Blog</a></li>
					<li><a href="/">Contact</a></li>
				
			</ul>			
		</nav>
	</header>
	
	<article>
			<p>
				<Counter />
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
				<p>
					<Articles />
				</p>
		</article>
		
	<aside>
			<p>
				<Hobbies />
			</p>

			<p>
				<News />
			</p>
				
	</aside>
		
	<footer>
		&copy; All rights reserved 2021
	</footer>
	
</div>

<style>
	nav {
		text-align: center;
		background-color: lightgreen;
		height: 3em;
		position:relative;
		border-radius: 8px;
		padding:0.4em
	}
	
	ul li {
		list-style: none;
		text-decoration: none;
		display: inline;
		margin-left: 1em;
		
	}
	
	article {
		grid-area: content;
		border-radius: 8px;
		padding:0px;
		margin:0px;
		background-color:lightcyan;
		margin-right: 8px;
		margin-bottom: 8px;
	}
	aside {
		grid-area: sidebar;
		background-color: lightcyan;
		border-radius: 8px;
	}
	aside, article{
		margin-top: 5px;
	}
	
	nav li a:hover {
		color: rgb(7, 54, 54);
	}
	nav li a:visted {
		color:rgb(179, 199, 182);
	}
	nav li a:hover {
		color:lightseagreen;
	}
	nav li a:active {
		color:rgb(107, 32, 178);
	}
	header{
		grid-area: header;
		height: 3em;
		border-radius: 8px;
	}
	footer{
		grid-area: footer;
		text-align:center;
		display: inline;
		border-radius:8px;
		background-color: lightgreen;
		height: 3em;
	}
	nav, footer {
	
		font-weight: bolder;
	}
	p {
		margin-left: 8px;
	}
	
	.wrapper {
		display: grid;
		height: 100vh;
		grid-gap: 1.5em;
		grid-template-columns: 3fr 1fr;
		grid-template-areas: 
		"header header"
		"content sidebar"
		"footer footer";
	}

		@media (max-width: 500px) {
			.wrapper {
				grid-template-columns: 1fr;
				grid-template-areas: 
				"header"
				"content"
				"sidebar"
				"footer";
			}
		}	
</style>