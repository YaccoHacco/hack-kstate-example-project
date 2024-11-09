<script>
	import List from '../lib/List.svelte';

	let listContents = $state([
		{ id: 0, name: 'Jack R' },
		{ id: 1, name: 'Dean B' }
	]);

	let nameInput = $state('');

	const addPerson = () => {
		listContents.push({ id: listContents.length, name: nameInput });
		nameInput = '';
	};
</script>

<div>
	A List
	<div>
		<List contents={listContents} />
	</div>
	<div>
		<input name="name" bind:value={nameInput} />
		<button onclick={addPerson}>Add</button>
	</div>
</div>

<style>
</style>
