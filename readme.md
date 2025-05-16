📄 Project Documentation: Web-Based Calculator
📌 Project Overview
This project is a simple web-based calculator built using HTML, CSS (external), and JavaScript. It performs the following arithmetic operations:

Addition (+)

Subtraction (-)

Multiplication (*)

Division (/)

Percentage (%)

Clear function (C)

🧱 Technology Stack
HTML5 – For structuring the interface

CSS3 – For styling (external stylesheet linked)

JavaScript (Vanilla) – For functionality and interactivity

🗂️ File Structure
csharp
Copy
Edit

🧾 Code Documentation
1. HTML (index.html)
🔹 Metadata Section
html
Copy
Edit
<head>
    <meta charset="UTF-8">
    <title>Calculator</title>
    <link rel="stylesheet" href="style.css">
</head>
Sets the page title and character encoding.

Links to an external CSS file for styling.

🔹 Body Structure
Calculator Container
html
Copy
Edit
<div class="calculator">
All calculator components are wrapped inside this container for layout and styling.

2. Input Fields
First Number Input
html
Copy
Edit
<label for="num1">First Number:</label>
<input type="text" id="num1">
Second Number Input
html
Copy
Edit
<label for="num2">Second Number:</label>
<input type="text" id="num2">
Result Output
html
Copy
Edit
<label for="result">Output:</label>
<input type="text" id="result" readonly>
Input fields take numeric values.

Output is read-only to prevent user edits.

3. Button Controls
html
Copy
Edit
<div class="button-container">
    <button onclick="calculate('+')">+</button>
    <button onclick="calculate('-')">-</button>
    <button onclick="calculate('*')">*</button>
    <button onclick="calculate('/')">/</button>
    <button class="percent" onclick="calculate('%')">%</button>
    <button class="clear" onclick="clearFields()">C</button>
</div>
Each button calls a JavaScript function when clicked:

Arithmetic buttons call calculate(operator).

C button calls clearFields() to reset fields.

🧠 JavaScript Logic
Function: calculate(operator)
Description:
Handles the calculation based on the operator passed (+, -, *, /, %).

javascript
Copy
Edit
function calculate(operator) {
    let num1 = parseFloat(document.getElementById('num1').value);
    let num2 = parseFloat(document.getElementById('num2').value);
    let result = 0;

    if (isNaN(num1) || (operator !== '%' && isNaN(num2))) {
        alert("Please enter valid numbers!");
        return;
    }

    switch (operator) {
        case '+':
            result = num1 + num2;
            break;
        case '-':
            result = num1 - num2;
            break;
        case '*':
            result = num1 * num2;
            break;
        case '/':
            if (num2 === 0) {
                alert("Cannot divide by zero!");
                return;
            }
            result = num1 / num2;
            break;
        case '%':
            result = num1 / 100;
            break;
    }

    document.getElementById('result').value = result;
}
Key Features:
Input Parsing: Uses parseFloat() to convert string inputs to floating-point numbers.

Input Validation:

Ensures inputs are numbers.

Prevents division by zero.

Switch Statement: Performs calculation based on the operator.

Output Display: Sets the result in the #result input field.

Function: clearFields()
Description:
Resets all input and output fields to empty.

javascript
Copy
Edit
function clearFields() {
    document.getElementById('num1').value = '';
    document.getElementById('num2').value = '';
    document.getElementById('result').value = '';
}
📋 Functional Summary
Feature	Description
Addition	Adds two numbers
Subtraction	Subtracts second number from the first
Multiply	Multiplies two numbers
Division	Divides first number by second (validates zero)
Percentage	Converts first number to percentage (÷ 100)
Clear	Empties all fields
Input Check	Alerts on invalid or empty input

🎨 Styling (style.css)
Note: Not included in the provided code, but should typically contain:

Centered layout (.calculator)

Responsive design

Button hover effects

Padded input fields

Error highlighting (optional)

🔐 Validation & Error Handling
Case	Handled?	Behavior
Non-numeric input	✅	Alert shown
Empty fields	✅	Alert shown
Division by zero	✅	Alert: “Cannot divide by zero”
Percentage with one input	✅	Only num1 required

💡 Suggested Improvements
Enhancement	Benefit
Use input type="number"	Limits input to numeric only
Add decimal point support	Improves precision
Display calculation history	Better UX
Keyboard input support	Accessibility and faster input
Modular JS file	Cleaner separation of concerns
Use ES6 features (let, const)	Improves readability and performance
Add theme toggle (dark mode)	Better aesthetics

✅ Conclusion
This calculator is a basic, functional example of a web-based arithmetic tool. It demonstrates the integration of HTML, CSS, and JavaScript to provide a user-friendly interface and responsive feedback system. It’s a great starting point for more advanced tools such as scientific calculators, currency converters, or form-based applications.