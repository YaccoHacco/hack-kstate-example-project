<script>
	export let contents = [];
</script>

{#each contents as content}
	<div>{content.id} | {content.name}</div>
{/each}
