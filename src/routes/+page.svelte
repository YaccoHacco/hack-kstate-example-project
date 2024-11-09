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

<div class="h-full w-full">
	A List
	<div class="grid grid-cols-2 gap-4">
		<List contents={listContents} />
	</div>
	<div>
		<input class="p-2" name="name" bind:value={nameInput} />
		<button
			class="bg-blue-700 rounded p-2 border-none text-white shadow shadow-black hover:bg-blue-600 cursor-pointer"
			onclick={addPerson}>Add</button
		>
	</div>
</div>

<style>
</style>
