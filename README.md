# Ex04 Simple Calculator - React Project
## Date:

## AIM
To  develop a Simple Calculator using React.js with clean and responsive design, ensuring a smooth user experience across different screen sizes.

## ALGORITHM
### STEP 1
Create a React App.

### STEP 2
Open a terminal and run:
  <ul><li>npx create-react-app simple-calculator</li>
  <li>cd simple-calculator</li>
  <li>npm start</li></ul>

### STEP 3
Inside the src/ folder, create a new file Calculator.js and define the basic structure.

### STEP 4
Plan the UI: Display screen, number buttons (0-9), operators (+, -, *, /), clear (C), and equal (=).

### STEP 5
Create a new file Calculator.css in src/ and add the styling.

### STEP 6
Open src/App.js and modify it.

### STEP 7
Start the development server.
  npm start

### STEP 8
Open http://localhost:3000/ in the browser.

### STEP 9
Test the calculator by entering numbers and operations.

### STEP 10
Fix styling issues and refine content placement.

### STEP 11
Deploy the website.

### STEP 12
Upload to GitHub Pages for free hosting.

## PROGRAM
HTML
```
import React, { useState } from "react";
import { evaluate } from "mathjs"; // Install mathjs using `npm install mathjs`
import "./App.css";

const App = () => {
  const [input, setInput] = useState("");

  const handleClick = (value) => {
    if (value === "AC") {
      setInput("");
    } else if (value === "⌫") {
      setInput(input.slice(0, -1)); // Remove the last character
    } else if (value === "=") {
      try {
        setInput(evaluate(input).toString()); // Use mathjs for evaluation
      } catch {
        setInput("Error");
      }
    } else {
      setInput(input + value);
    }
  };

  return (
    <div className="calculator">
      <h1 className="title">Quick Math</h1>
      <div className="display" aria-label="Calculator display">
        {input || "0"}
      </div>
      <div className="buttons">
        <button
          className="btn-ac"
          onClick={() => handleClick("AC")}
          aria-label="Clear All"
        >
          AC
        </button>
        <button
          className="btn-special"
          onClick={() => handleClick("⌫")}
          aria-label="Backspace"
        >
          ⌫
        </button>
        <button
          className="btn-operator"
          onClick={() => handleClick("%")}
          aria-label="Percentage"
        >
          %
        </button>
        <button
          className="btn-operator"
          onClick={() => handleClick("/")}
          aria-label="Divide"
        >
          /
        </button>

        <button
          className="btn-number"
          onClick={() => handleClick("7")}
          aria-label="Seven"
        >
          7
        </button>
        <button
          className="btn-number"
          onClick={() => handleClick("8")}
          aria-label="Eight"
        >
          8
        </button>
        <button
          className="btn-number"
          onClick={() => handleClick("9")}
          aria-label="Nine"
        >
          9
        </button>
        <button
          className="btn-operator"
          onClick={() => handleClick("*")}
          aria-label="Multiply"
        >
          *
        </button>

        <button
          className="btn-number"
          onClick={() => handleClick("4")}
          aria-label="Four"
        >
          4
        </button>
        <button
          className="btn-number"
          onClick={() => handleClick("5")}
          aria-label="Five"
        >
          5
        </button>
        <button
          className="btn-number"
          onClick={() => handleClick("6")}
          aria-label="Six"
        >
          6
        </button>
        <button
          className="btn-operator"
          onClick={() => handleClick("-")}
          aria-label="Subtract"
        >
          -
        </button>

        <button
          className="btn-number"
          onClick={() => handleClick("1")}
          aria-label="One"
        >
          1
        </button>
        <button
          className="btn-number"
          onClick={() => handleClick("2")}
          aria-label="Two"
        >
          2
        </button>
        <button
          className="btn-number"
          onClick={() => handleClick("3")}
          aria-label="Three"
        >
          3
        </button>
        <button
          className="btn-operator"
          onClick={() => handleClick("+")}
          aria-label="Add"
        >
          +
        </button>

        <button
          className="btn-number"
          onClick={() => handleClick("0")}
          aria-label="Zero"
        >
          0
        </button>
        <button
          className="btn-number"
          onClick={() => handleClick(".")}
          aria-label="Decimal"
        >
          .
        </button>
        <button
          className="btn-equal"
          onClick={() => handleClick("=")}
          aria-label="Equals"
        >
          =
        </button>
      </div>

      <footer>
        <p>DEVELOPED BY Mohamed Athif Rahuman J</p>
        <p>Reg No: 212223220058</p>
      </footer>
    </div>
  );
};

export default App;
```
CSS
```
body {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  background: linear-gradient(135deg, #6a11cb, #2575fc);
  margin: 0;
  font-family: Arial, sans-serif;
}

.calculator {
  background: rgba(255, 255, 255, 0.1);
  padding: 20px;
  border-radius: 15px;
  box-shadow: 0px 10px 20px rgba(0, 0, 0, 0.3);
  text-align: center;
  width: 320px;
  backdrop-filter: blur(10px);
}

h1 {
  margin: 10px 0;
  font-size: 28px;
  font-weight: bold;
  color: #fff;
  text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.5);
}

.display {
  background-color: #000;
  color: #0f0;
  width: 100%;
  height: 60px;
  text-align: right;
  font-size: 24px;
  border-radius: 10px;
  padding: 10px;
  box-sizing: border-box;
  margin-bottom: 20px;
  font-family: "Courier New", Courier, monospace;
  box-shadow: inset 0px 0px 5px rgba(0, 0, 0, 0.5);
}

.buttons {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 15px;
}

button {
  width: 100%;
  height: 60px;
  font-size: 20px;
  border: none;
  border-radius: 10px;
  background: linear-gradient(135deg, #ffffff, #d4d4d4);
  box-shadow: 2px 4px 6px rgba(0, 0, 0, 0.2);
  cursor: pointer;
  transition: all 0.2s ease-in-out;
}

button:hover {
  background: linear-gradient(135deg, #f0f0f0, #c0c0c0);
  transform: translateY(-2px);
}

button:active {
  transform: scale(0.95);
  box-shadow: inset 2px 2px 5px rgba(0, 0, 0, 0.3);
}

.btn-ac {
  background: linear-gradient(135deg, #ff4b4b, #ff0000);
  color: white;
}

.btn-ac:hover {
  background: linear-gradient(135deg, #ff6b6b, #ff3333);
}

.btn-special {
  background: linear-gradient(135deg, #ffa500, #ff7f00);
  color: white;
}

.btn-special:hover {
  background: linear-gradient(135deg, #ffb733, #ff9933);
}

.btn-operator {
  background: linear-gradient(135deg, #4caf50, #388e3c);
  color: white;
}

.btn-operator:hover {
  background: linear-gradient(135deg, #66bb6a, #43a047);
}

.btn-equal {
  background: linear-gradient(135deg, #2196f3, #1976d2);
  color: white;
  grid-column: span 2;
}

.btn-equal:hover {
  background: linear-gradient(135deg, #42a5f5, #1e88e5);
}

.footer {
  margin-top: 20px;
  font-size: 14px;
  color: #fff;
  text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.5);
}

.footer p {
  margin: 5px 0;
}
```

## OUTPUT
![Screenshot 2025-04-01 124052](https://github.com/user-attachments/assets/f6f7fc96-fca4-4999-844a-7f1ac9ca8fb6)


## RESULT
The program for developing a simple calculator in React.js is executed successfully.
