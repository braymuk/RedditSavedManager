<script>
	export let name;
</script>

<main>
	<h1>Your Saved Feed {name}!</h1>
	<div id="feed">
		<div class="item">
			<div class ="title">Post 1</div>
			<img src = "./images/test.jpeg">
		</div>
		<div class="item">
			<div class ="title">Post 2</div>
			<img src = "./images/test2.jpeg">
		</div>
	</div>
	
</main>

<style>
	main {
		display:flex;
		flex-direction: column;
		height:100%;
		width:100%;
	}

	#feed{
		display:grid;
		justify-self: center;
		width:100%;
		height:100%;
		grid-template-columns: 1fr 1fr 1fr 1fr;
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

	
</style>