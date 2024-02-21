<script>
    import Header from './header.svelte';
    import TasksList from './tasksList.svelte';
    import AddTask from './addTask.svelte';

    let taskList = []

    function addNewTask (event) {
        let newTask = event.detail.inputValue;
        taskList = [...taskList, newTask];
    }

    function deleteTask (event) {
        taskList = taskList.filter ((t) => t !== event.detail.task);
    }

</script>

<Header />
<TasksList taskList={taskList} on:delete={deleteTask}/>
<AddTask on:message={addNewTask} />

