<script>
	import { createEventDispatcher } from 'svelte';
	export let taskList;

	const dispatch = createEventDispatcher();

	function deleteTask (task) {
		dispatch ('delete', task);
	}

</script>

{#each taskList as task}
	<div class="task">
		<input type="checkbox" />
		<div class="taskName">{task}</div>
		<button on:click={() => deleteTask({task})}>X</button>
	</div>
{/each}

<style>
	.task {
		display: grid;
		grid-template-columns: repeat(10, minmax(min-content, 30px));
	}

	input {
		grid-column: 1/2;
	}

	.taskName {
		grid-column: 2/10;
	}

	button {
		grid-column: 10;
	}
</style>
