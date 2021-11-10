<script lang="ts">
	export let name: string;
	export let isAnonimous: boolean = false;

	$: userName = isAnonimous ? 'Anonimous' : name;

	function changeName(e: any) {
		name = e.target.value;
	}
</script>

<main>
	<h1>
		Hello {userName}
		{#if isAnonimous}
			<span>🥸</span>
		{:else}
			<span>🤓</span>
		{/if}
	</h1>
	<input type="text" bind:value={name} on:change={changeName} />
	<label>
		<input type=checkbox bind:checked={isAnonimous}>
		<span>anonimous</span>
	</label>

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