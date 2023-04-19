document.addEventListener('DOMContentLoaded', () => {
    const taskForm = document.getElementById('task-form');
    const taskInput = document.getElementById('task-input');
    const taskList = document.getElementById('task-list');

    taskForm.addEventListener('submit', (e) => {
        e.preventDefault();
        addTask(taskInput.value);
        taskInput.value = '';
    });

    taskList.addEventListener('click', (e) => {
        if (e.target.tagName === 'SPAN') {
            e.target.parentElement.remove();
        }
    });

    function addTask(task) {
        const li = document.createElement('li');
        li.textContent = task;
        const deleteBtn = document.createElement('span');
        deleteBtn.textContent = 'X';
        li.appendChild(deleteBtn);
        taskList.appendChild(li);
    }
});
