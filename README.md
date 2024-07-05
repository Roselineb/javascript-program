# javascript-program


# Exercise 1: Let and Const
```
let age=30;
const name="Alice";
 name="bob";
 console.log(name)
```
## Output:
![ex1-const](https://github.com/Roselineb/javascript-program/assets/128909895/d7caed67-e5f2-4caa-b336-dcd36346f26a)

# Exercise 2: Arrow Functions
```
const add=(a,b)=>{
    console.log(a+b) ;
}
add(4,6);
```
## Output:
![ex2-arrow function](https://github.com/Roselineb/javascript-program/assets/128909895/a2b50e86-8afb-495e-af90-9a9b42aeab55)

# Exercise 3: Template Literals
```
let name="Alice";
let age=30;
let txt=`Hello,${name} Your age is ${age}.`;
console.log(txt);
```
## Output:
![ex3-templateliteral](https://github.com/Roselineb/javascript-program/assets/128909895/9d9a3984-641c-4cb5-87e8-76b3fc02faef)

# Exercise 4: Destructuring Objects
```
const person={
    firstName: "Alice", 
    lastName: "Johnson"
}
const{firstName,lastName}=person;
console.log(firstName);
console.log(lastName)
```
## Output:
![ex4-Destructuring Objects](https://github.com/Roselineb/javascript-program/assets/128909895/64de1dea-b62d-40aa-afb5-901d17bd39d2)

# Exercise 5: Destructuring Arrays
```
const numbers = [1, 2, 3, 4, 5];

const [first, second] = numbers;

console.log(first);  
console.log(second);
```
## Output:
![ex5- Desarray](https://github.com/Roselineb/javascript-program/assets/128909895/cfafc407-1cdb-4747-a68f-fae6d4d6b494)

# Exercise 6: Spread Operator
```
const arr1 = [1, 2, 3];
const arr2 = [4, 5, 6];

const combined = [...arr1, ...arr2];

console.log(combined);
```
## Output:
![ex6-Spread Operator](https://github.com/Roselineb/javascript-program/assets/128909895/eaa503f5-871d-404a-bf1a-718ce6381691)

# Exercise 7: Rest Parameters
```
const sum = (...numbers) => numbers.reduce((acc, current) => acc + current, 0);

console.log(sum(1, 2, 3, 4, 5)); 
console.log(sum(10, 20));        
console.log(sum());
```
## Output:
![ex7-Rest Parameters](https://github.com/Roselineb/javascript-program/assets/128909895/d3c6f1eb-f10e-4414-9d60-7d8fb7b1c3d1)
# Exercise 8: Default Parameters
```
const greet = (name, greeting = "Hello") => `${greeting}, ${name}!`;

console.log(greet("Alice"));          
console.log(greet("Bob", "Hi"));      
console.log(greet("Charlie", "Hey"));
```

## Output:
![ex8-Default Parameters](https://github.com/Roselineb/javascript-program/assets/128909895/11542c07-b19d-42e1-aff4-56ef44dd0be8)

# Exercise 9: Classes and Inheritance
```
class Animal {
    constructor(name) {
      this.name = name;
    }
  }
  
  class Dog extends Animal {
    bark() {
      return `Woof! My name is ${this.name}`;
    }
  }
  
  const myDog = new Dog('Buddy');
  console.log(myDog.bark());
```
## Output:
![ex9-Classes and Inheritance](https://github.com/Roselineb/javascript-program/assets/128909895/4d7644d0-a1da-4ca9-be66-0bd9312c989f)

# Exercise 10: Promises and Async/Await
```
const waitAndReturn = () => 
    new Promise(resolve => setTimeout(() => resolve("Done"), 2000));
  
  async function run() {
    const result = await waitAndReturn();
    console.log(result); 
  }
  
  run();
```
## Output:
![ex10-async](https://github.com/Roselineb/javascript-program/assets/128909895/63ace027-047e-49d2-b0d6-96ad8f7067f3)
# TO-DO-LIST PROJECT
## javascript:
```
document.addEventListener('DOMContentLoaded', () => {
    const addButton = document.getElementById('add-btn');
    const todoInput = document.getElementById('todo-input');
    const todoList = document.getElementById('todo-list');
    const filter = document.getElementById('filter');

    addButton.addEventListener('click', addTodo);
    todoList.addEventListener('click', handleTodoClick);
    filter.addEventListener('change', filterTodos);

    function addTodo() {
        const todoText = todoInput.value.trim();
        if (todoText !== '') {
            const li = document.createElement('li');
            li.textContent = todoText;
            li.classList.add('todo-item');

            const completeBtn = document.createElement('button');
            completeBtn.textContent = 'Complete';
            completeBtn.classList.add('complete-btn');
            li.appendChild(completeBtn);

            const deleteBtn = document.createElement('button');
            deleteBtn.textContent = 'Delete';
            deleteBtn.classList.add('delete-btn');
            li.appendChild(deleteBtn);

            todoList.appendChild(li);
            todoInput.value = '';
        }
    }

    function handleTodoClick(e) {
        const item = e.target;

        if (item.classList[0] === 'delete-btn') {
            item.parentElement.remove();
        }

        if (item.classList[0] === 'complete-btn') {
            const todo = item.parentElement;
            todo.classList.toggle('completed');
        }
    }

    function filterTodos() {
        const todos = todoList.childNodes;
        todos.forEach(todo => {
            switch (filter.value) {
                case 'all':
                    todo.style.display = 'flex';
                    break;
                case 'completed':
                    if (todo.classList.contains('completed')) {
                        todo.style.display = 'flex';
                    } else {
                        todo.style.display = 'none';
                    }
                    break;
                case 'uncompleted':
                    if (!todo.classList.contains('completed')) {
                        todo.style.display = 'flex';
                    } else {
                        todo.style.display = 'none';
                    }
                    break;
            }
        });
    }
});
```
## CSS:
```
body {
    font-family: Arial, sans-serif;
    background-color:white;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    margin: 0;
}

/* .container {
    background: white;
    padding: 20px;
    border-radius: 5px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    width: 300px;
    text-align: center;
} */

h1 {
    margin-bottom: 20px;
}

.input-container, .filter-container {
    display: flex;
    justify-content: space-between;
    margin-bottom: 10px;
}

#todo-input, #filter {
    width: 70%;
    padding: 10px;
    border: 1px solid #ccc;
    border-radius: 5px;
}

#add-btn {
    padding: 10px;
    border: none;
    background-color: #28a745;
    color: white;
    border-radius: 5px;
    cursor: pointer;
}

#add-btn:hover {
    background-color: #218838;
}

ul {
    list-style: none;
    padding: 0;
}

li {
    background: #f4f4f4;
    padding: 10px;
    border-bottom: 1px solid #ddd;
    display: flex;
    justify-content: space-between;
    align-items: center;
}

li.completed {
    text-decoration: line-through;
    background: #d4edda;
}

li button {
    border: none;
    background: #dc3545;
    color: white;
    padding: 5px 10px;
    border-radius: 5px;
    cursor: pointer;
}

li button:hover {
    background: #c82333;
}

li .complete-btn {
    background: #007bff;
    margin-right: 5px;
}

li .complete-btn:hover {
    background: #0069d9;
}
```
## Html:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>To-Do List</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div class="container">
        <h1>To-Do List</h1>
        <div class="input-container">
            <input type="text" id="todo-input" placeholder="Add a new task">
            <button id="add-btn">Add</button>
        </div>
        <div class="filter-container">
            <select id="filter">
                <option value="all">All</option>
                <option value="completed">Completed</option>
                <option value="uncompleted">Uncompleted</option>
            </select>
        </div>
        <ul id="todo-list"></ul>
    </div>
    <script src="script.js"></script>
</body>
</html>
```
# output:
![image](https://github.com/Roselineb/javascript-program/assets/128909895/7c7c26d9-08d8-4386-8700-19120109aad1)




























