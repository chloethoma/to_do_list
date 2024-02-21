<script>
    import Header from './header.svelte';
    import TasksList from './tasksList.svelte';
    import AddTask from './addTask.svelte';

    let taskList = []

    function addNewTask (event) {
        let newTask = event.detail.inputValue
        taskList = [...taskList, newTask]
    }

</script>

<Header />
<TasksList taskList={taskList}/>
<AddTask on:message={addNewTask} />

