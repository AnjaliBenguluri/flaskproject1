# flaskproject1
#index.html

<!-- app/templates/index.html -->
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>User Form</title>
    <link rel="stylesheet" href="{{ url_for('static', filename='css/style.css') }}">
</head>
<body>
    <div class="container">
        <h2>User Information Form</h2>
        <form id="userForm" action="/submit" method="POST">
            <label for="username">Username:</label>
            <input type="text" id="username" name="username" required>

            <label for="phone">Phone Number:</label>
            <input type="text" id="phone" name="phone" required>

            <label for="email">Email:</label>
            <input type="email" id="email" name="email" required>

            <button type="submit">Submit</button>
        </form>
    </div>
    <script src="{{ url_for('static', filename='js/script.js') }}"></script>
</body>
</html>
#style.css

[7:31 PM, 10/22/2024] bengulurianjali: /* app/static/css/style.css */
body {
    font-family: Arial, sans-serif;
    background-color: #1a1a1a; /* Dark Background */
    color: #fff; /* Text color */
}

.container {
    width: 50%;
    margin: 0 auto;
    padding: 20px;
    background-color: #333;
    border-radius: 10px;
    box-shadow: 0 0 10px rgba(255, 255, 255, 0.1);
}

input, button {
    width: 100%;
    padding: 10px;
    margin: 10px 0;
    border: none;
    border-radius: 5px;
}

button {
    background-color: #4CAF50;
    color: white;
    cursor: pointer;
}

#javascript

[7:32 PM, 10/22/2024] bengulurianjali: // app/static/js/script.js
document.getElementById('userForm').addEventListener('submit', function(event) {
    const phone = document.getElementById('phone').value;
    if (!/^\d+$/.test(phone)) {
        alert("Please enter a valid phone number.");
        event.preventDefault();
    }
});
[7:33 PM, 10/22/2024] bengulurianjali: # app/_init_.py
from flask import Flask

def create_app():
    app = Flask(_name_)
    
