index.html

<!DOCTYPE html>
<html>
<head>
    <title>Expense Tracker</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

<div class="container">
    <h1>Expense Tracker</h1>

    <input type="text" id="name" placeholder="Expense name">
    <input type="number" id="amount" placeholder="Amount">

    <button onclick="addExpense()">Add Expense</button>

    <h2>Total: ₹<span id="total">0</span></h2>

    <ul id="expenseList"></ul>
</div>

<script src="script.js"></script>
</body>
</html>

style.css

body {
    font-family: Arial;
    background: #f2f2f2;
}

.container {
    width: 400px;
    margin: 80px auto;
    padding: 25px;
    background: white;
    border-radius: 10px;
}

input {
    width: 90%;
    padding: 10px;
    margin: 5px;
}

button {
    padding: 10px;
    margin: 10px;
    cursor: pointer;
}

li {
    list-style: none;
    padding: 10px;
    margin: 5px;
    background: #eee;
}

script.js

let total = 0;

function addExpense() {
    let name = document.getElementById("name").value;
    let amount = Number(document.getElementById("amount").value);

    if (name === "" || amount <= 0) {
        alert("Enter valid details");
        return;
    }

    total = total + amount;

    let li = document.createElement("li");
    li.innerText = name + " - ₹" + amount;

    document.getElementById("expenseList").appendChild(li);

    document.getElementById("total").innerText = total;

    document.getElementById("name").value = "";
    document.getElementById("amount").value = "";
}# expense-tracker-
