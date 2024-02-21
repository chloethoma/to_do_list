<script>
    import { createEventDispatcher } from "svelte";
    export let task;

    const dispatch = createEventDispatcher();
    let isDone = false;

    function deleteTask (task) {
		dispatch ('delete', task);
	}
</script>

<div class="task">
    <input type="checkbox" bind:checked={task.done} on:click={() => isDone = !isDone} />
    <div class="taskName" class:isDone>{task.name}</div>
    <button on:click={() => deleteTask({task})}>X</button>
</div>

<style>
	.task {
		display: grid;
		grid-template-columns: repeat(10, minmax(min-content, 30px));
	}

	input {
		grid-column: 1/2;
	}

	.taskName.isDone {
		text-decoration-line: line-through;
	}

	.taskName {
		grid-column: 2/10;
	}

	button {
		grid-column: 10;
	}
</style>

