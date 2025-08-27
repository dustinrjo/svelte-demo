<script>
	let inputValue = '';

	export { inputValue };
</script>

<div>
	<label for="user-input">Enter text:</label>
	<input
		id="user-input"
		type="text"
		bind:value={inputValue}
		placeholder="Type something here..."
	/>
</div>

<style>
	div {
		margin: 1rem 0;
	}
	
	label {
		display: block;
		margin-bottom: 0.5rem;
		font-weight: bold;
	}
	
	input {
		padding: 0.5rem;
		border: 1px solid #ccc;
		border-radius: 4px;
		width: 300px;
	}
</style>