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
App.jsx
~~~
import React from 'react';
import Calculator from './calculator.jsx';

function App() {
  return (
    <div className="App">
      <Calculator />
    </div>
  );
}
export default App;
~~~
Calculator.css
~~~
.calculator {
    max-width: 400px;
    margin: 50px auto;
    padding: 20px;
    border-radius: 12px;
    background: #f9f9f9;
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.2);
  }
  
  .display {
    height: 60px;
    background: #333;
    color: #fff;
    font-size: 2rem;
    padding: 10px;
    text-align: right;
    border-radius: 8px;
    overflow-x: auto;
  }
  
  .buttons {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 12px;
    margin-top: 20px;
  }
  
  button {
    padding: 20px;
    font-size: 1.2rem;
    border: none;
    border-radius: 8px;
    background-color: #e0e0e0;
    cursor: pointer;
    transition: background-color 0.2s ease;
  }
  
  button:hover {
    background-color: #d0d0d0;
  }
  ~~~
Calculator.jsx
~~~
import React, { useState } from 'react';
import './Calculator.css';

const Calculator = () => {
  const [input, setInput] = useState('');

  const handleClick = (value) => {
    if (value === '=') {
      try {
        setInput(eval(input).toString());
      } catch {
        setInput('Error');
      }
    } else if (value === 'C') {
      setInput('');
    } else {
      setInput((prev) => prev + value);
    }
  };

  return (
    <div className="calculator">
      <div className="display">{input || '0'}</div>
      <div className="buttons">
        {['7','8','9','/','4','5','6','*','1','2','3','-','0','.','=','+','C'].map((btn) => (
          <button key={btn} onClick={() => handleClick(btn)}>{btn}</button>
        ))}
      </div>
    </div>
  );
};

export default Calculator;
~~~
## OUTPUT
<img width="1919" height="965" alt="439973181-10f44c3a-f5ae-42f7-bfe3-0ac2bba5246f" src="https://github.com/user-attachments/assets/cdb5843e-7644-4cfe-9f7e-38edf3cf55ac" />

<img width="1917" height="956" alt="439973330-3edf328b-99e3-4a15-a7a7-9eeea4bc11ab" src="https://github.com/user-attachments/assets/e20f584c-1735-42e8-be41-182592ed6389" />

<img width="1919" height="960" alt="439973380-7a17dffa-903d-48a1-8e97-5a226f6e9e93" src="https://github.com/user-attachments/assets/f50bd485-43c7-4076-a7e6-2bbc251bb717" />


## RESULT
The program for developing a simple calculator in React.js is executed successfully.
