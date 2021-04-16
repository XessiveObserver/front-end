<script>
import Counter from "./Counter.svelte";
import Games from "./Games.svelte";
import Hobbies from "./Hobbies.svelte";
import News from "./News.svelte";
import Topics from "./Topics.svelte";



	
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

		</article>
	</section>
		
	<aside>
		<section>
			<p>
				<Hobbies />
			</p>

			<p>
				<News />
			</p>
			
		</section>		
	</aside>
		
	<footer>
		&copy; All rights reserved 2021
	</footer>
	
</main>

<style>
	

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