<script>
	export let name;
	let beltColor = "blue";
	let firstName = "Tom"
	let lastName = "Black"
	$: fullName = `${firstName} ${lastName}`;
	let people = [
		{fullName: "Tom Black", beltColor: "Black", id: 1},
		{fullName: "Ashley Black", beltColor: "Black", id: 2},
		{fullName: "David Richards", beltColor: "Orange", id: 3},
		{fullName: "Shayne Black", beltColor: "Green", id: 4}
	]

	const handleClick = () => {
		if(beltColor === "orange"){
			beltColor = "blue"
		} 
		else 
		{
			beltColor = "orange"
		}
	};

	const handleInput = (e) => {
		beltColor = e.target.value;
	}
</script>

<main>
	<h1>Hello {name}!</h1>
	<p style="color: {beltColor}; font-weight: bold">The belt color is: {beltColor}</p>
	<p>Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn how to build Svelte apps.</p>
	<p>Full Name: {fullName}</p>
	<button on:click={handleClick}>Change the belt color!</button>
	<input type="text" bind:value={beltColor}>
	<input type="text" bind:value={firstName}>
	<input type="text" bind:value={lastName}>

	{#each people as person (person.id)}
		<div>Name: {person.fullName}</div>
		<div>Belt Color: {person.beltColor}</div>
		<br>
	{:else}
		<div> There's no people to show at this time...</div>
	{/each}
	<!-- on:input={handleInput} value={beltColor} -->
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