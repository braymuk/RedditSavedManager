<script>
	import {onMount} from "svelte";
	const endpoint = "https://jsonplaceholder.typicode.com/photos";
	let posts = [];

	onMount(async function () {
		const response = await fetch(endpoint);
		const data = await response.json();
		console.log(data);
		posts = data;
	});

	
	export let name;
	export let item;
</script>

<main>
	<h1 id="pageTitle">SaveIt! {name}!</h1>
	<div id="pageWrapper">
		
		<div id="feed">
			<div class="item">
				<div class ="title">Post 1</div>
				<img src = "./images/test.jpeg">
			</div>
			<div class="item">
				<div class ="title">Post 2</div>
				<img src = "./images/test2.jpeg">
			</div>

			{#each posts as article} 
				<div class = "item">
					<div class ="title">{article.title}</div>
					<img src = "{article.url}">
				</div>
				
			{/each}

		</div>
	</div>
</main>

<style>
	main {
		
	}

	#pageTitle {
		margin-left: 1%;
		margin-right: auto;
	}

	#pageWrapper {
		display:flex;
		justify-content: center;
	}

	#feed{
		display:grid;
		justify-self: center;
		width:100%;
		height:100%;
		grid-template-columns: 1fr 1fr 1fr;
		column-gap: 20px;
		row-gap: 10px;
		max-width: 1152px;
	}

	.item{
		width:100%;
		display:flex;
		flex-direction: column;
	
	}

	.item img {
		width:100%;
		object-fit: contain;
	}

	.title{
		padding:3px;
	}

	
</style>