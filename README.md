-<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ToDo List</title>
    <style>
        body {
            font-family: Arial, sans-serif;
        }
        .container {
            max-width: 400px;
            margin: 20px auto;
            padding: 0 20px;
        }
        h2 {
            text-align: center;
        }
        input[type="text"] {
            width: 100%;
            padding: 10px;
            margin-bottom: 10px;
            box-sizing: border-box;
        }
        ul {
            list-style-type: none;
            padding: 0;
        }
        li {
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 10px;
            border-bottom: 1px solid #ddd;
        }
        .delete-btn {
            background-color: #ff7b7b;
            color: #fff;
            border: none;
            padding: 5px 10px;
            cursor: pointer;
            border-radius: 5px;
        }
    </style>
</head>
<body>

<div class="container">
    <h2>ToDo List</h2>
    <input type="text" id="taskInput" placeholder="Add new task">
    <button onclick="addTask()">Add Task</button>
    <ul id="taskList">
    </ul>
</div>

<script>
    function addTask() {
        var taskInput = document.getElementById("taskInput");
        var taskList = document.getElementById("taskList");

        if (taskInput.value.trim() === "") {
            alert("Please enter a task!");
            return;
        }

        var li = document.createElement("li");
        li.textContent = taskInput.value;

        var deleteBtn = document.createElement("button");
        deleteBtn.textContent = "Delete";
        deleteBtn.classList.add("delete-btn");
        deleteBtn.onclick = function() {
            li.remove();
        };

        li.appendChild(deleteBtn);
        taskList.appendChild(li);

        taskInput.value = "";
    }
</script>

</body>
</html>
