<script>
	import { createEventDispatcher } from 'svelte';
	import Task from './task.svelte';
	export let taskList;

	const dispatch = createEventDispatcher();

	function deleteTask (event) {
		dispatch('delete', event.detail)
	}

</script>

{#each taskList as task}
<Task task={task} on:delete={deleteTask} />
{/each}

<!-- {JSON.stringify(task)} -->
