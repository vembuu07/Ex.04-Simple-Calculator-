# MWAD-EXP_04-Simple-caluculator
## Date:16.11.2025

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

App.css

```
body {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  background: #9ebc8a;
  font-family: Georgia;
}

.calc {
  background: #73946b;
  padding: 20px;
  border-radius: 10px;
  text-align: center;
}

#display {
  width: 160px;
  height: 30px;
  margin-bottom: 10px;
  font-size: 1.2em;
  text-align: right;
}

button {
  width: 40px;
  height: 40px;
  margin: 5px;
  font-size: 1.1em;
  cursor: pointer;
}
```

App.jsx

```
import React, { useState } from "react";
import "./App.css"; // You can put the styles in a CSS file or inline

function Calculator() {
  const [display, setDisplay] = useState("");

  const press = (val) => {
    setDisplay((prev) => prev + val);
  };

  const calc = () => {
    try {
      // Evaluate expression safely
      // eslint-disable-next-line no-eval
      setDisplay(eval(display).toString());
    } catch (error) {
      setDisplay("Error");
    }
  };

  const clr = () => {
    setDisplay("");
  };

  return (
    <div className="calc">
      <input id="display" value={display} readOnly />
      <br />
      <div>
        <button onClick={() => press("1")}>1</button>
        <button onClick={() => press("2")}>2</button>
        <button onClick={() => press("3")}>3</button>
        <button onClick={() => press("+")}>+</button>
      </div>
      <div>
        <button onClick={() => press("4")}>4</button>
        <button onClick={() => press("5")}>5</button>
        <button onClick={() => press("6")}>6</button>
        <button onClick={() => press("-")}>-</button>
      </div>
      <div>
        <button onClick={() => press("7")}>7</button>
        <button onClick={() => press("8")}>8</button>
        <button onClick={() => press("9")}>9</button>
        <button onClick={() => press("*")}>*</button>
      </div>
      <div>
        <button onClick={clr}>C</button>
        <button onClick={() => press("0")}>0</button>
        <button onClick={calc}>=</button>
        <button onClick={() => press("/")}>/</button>
      </div>
    </div>
  );
}

export default Calculator;
```
## OUTPUT
<img width="1909" height="1134" alt="image" src="https://github.com/user-attachments/assets/42f18524-2209-406f-b14d-c46b5e187298" />

## RESULT
The program for developing a simple calculator in React.js is executed successfully.

## RESULT
The program for developing a simple calculator in React.js is executed successfully.
