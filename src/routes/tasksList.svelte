<script>
	import Task from './task.svelte';
	export let taskList;

</script>

{#each taskList as task}
<Task task={task} on:delete />
{/each}

<!-- {JSON.stringify(task)} -->
