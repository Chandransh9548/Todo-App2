# HTML for Todo App
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Todo App</title>
    <link rel="stylesheet"href="style.css">
</head>
<body>
        <h1>Todo App</h1>
        <input placeholder="Add your Task">
        <button>Add Task</button>
        <ul>
            <li>Eat<button class="delete">Delete</button></li>
            <li>Potato<button class="delete">Delete</button></li>
        </ul>
        <script src="app.js"></script>
</body>
</html>



# CSS for ToDo App 

/* Reset and base styles */
body, h1, ul, li, input, button {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}

/* Body styling with attractive animated background */
 body {
    background-image: url('download.jpeg'); /* Replace with your image path */
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 40px 20px;
    border: 6px solid transparent;
    border-image: linear-gradient(to right, #ff6a00, #ee0979);
    border-image-slice: 1;
    border-radius: 20px;
    box-shadow: 0 0 20px rgba(255, 105, 180, 0.3);
}


/* Gradient animation */
@keyframes gradientShift {
    0% { background-position: 0% 50%; }
    50% { background-position: 100% 50%; }
    100% { background-position: 0% 50%; }
}

/* Header */
h1 {
    color: #333;
    font-size: 2.5rem;
    margin-bottom: 30px;
    padding-bottom: 10px;
    border-bottom: 3px solid #ee0979;
    text-shadow: 1px 1px 2px rgba(0,0,0,0.2);
}

/* Input and button */
input {
    padding: 12px 16px;
    font-size: 1rem;
    border: 2px solid #ff6a00;
    border-radius: 10px;
    width: 250px;
    margin-right: 10px;
    transition: all 0.3s ease;
}

input:focus {
    border-color: #ee0979;
    outline: none;
    box-shadow: 0 0 8px #ee0979;
}

button {
    padding: 12px 20px;
    font-size: 1rem;
    background: linear-gradient(to right, #ff6a00, #ee0979);
    color: white;
    border: none;
    border-radius: 10px;
    cursor: pointer;
    transition: transform 0.2s ease;
}

button:hover {
    transform: scale(1.05);
}

/* Task list */
ul {
    list-style: none;
    margin-top: 30px;
    width: 320px;
    padding: 15px;
    border: 3px dashed #ee0979;
    border-radius: 15px;
    background-color: rgba(255, 255, 255, 0.4);
    backdrop-filter: blur(5px);
}

li {
    background-color: white;
    padding: 12px 16px;
    margin-bottom: 12px;
    border: 2px solid #ff6a00;
    border-radius: 10px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    box-shadow: 0 4px 6px rgba(0,0,0,0.1);
    transition: box-shadow 0.3s ease;
}

li:hover {
    box-shadow: 0 6px 10px rgba(0,0,0,0.2);
}

/* Delete button */
.delete {
    background-color: #dc3545;
    color: white;
    border: 2px solid #a71d2a;
    padding: 6px 12px;
    border-radius: 8px;
    cursor: pointer;
    transition: background-color 0.3s ease;
}

.delete:hover {
    background-color: #a71d2a;
}


# Java Script for ToDo App
let btn=document.querySelector("button");
let ul=document.querySelector("ul");
let inp=document.querySelector("input");
btn.addEventListener("click",function(){
    let item=document.createElement("li");
    item.innerText=inp.value;

    let delBtn=document.createElement("button");
    delBtn.innerText="delete";
    delBtn.classList.add("delete");
    item.appendChild(delBtn);
    ul.appendChild(item);
    inp.value="";
});

// let delBtns=document.querySelectorAll(".delete");
// for(delBtn of delBtns){
//     delBtn.addEventListener("click",function() {
//   let par = this.parentElement;
//   console.log(par);
//         par.remove();
//     });
// }
ul.addEventListener("click",function(event){
 if (event.target.nodeName == "BUTTON"){
  let listItem=event.target.parentElement;
 listItem.remove();
  console.log("delete");
 }
});
