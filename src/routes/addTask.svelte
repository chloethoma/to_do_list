<script>
	import { createEventDispatcher } from 'svelte';
	let inputValue = '';

	const dispatch = createEventDispatcher();

	const sendMessageForNewTask = () => {
		dispatch('message',{inputValue});
	};
</script>

<div class="addTask">
	<button on:click={sendMessageForNewTask}>+</button>
	<input bind:value={inputValue} placeholder="Add to-do" />
</div>

<style>
	.addTask {
		display: grid;
		grid-template-columns: repeat(2, minmax(min-content, 30px));
	}

	button {
		grid-column: 1;
	}

	input {
		grid-column: 2;
	}
</style>