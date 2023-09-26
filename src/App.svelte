<script>
	export let name;
	let beltColor = "blue";

	const handleClick = () => {
		if(beltColor === "orange"){
			beltColor = "blue"
		} 
		else 
		{
			beltColor = "orange"
		}

	};
</script>

<main>
	<h1>Hello {name}!</h1>
	<p>The belt color is: {beltColor}</p>
	<p>Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn how to build Svelte apps.</p>
	<button on:click={handleClick}>Change the belt color!</button>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>