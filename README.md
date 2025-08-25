<!DOCTYPE html><html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Simple Calculator</title>
  <style>
    body {
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      background: #f3f4f6;
      font-family: Arial, sans-serif;
    }
    .calculator {
      background: #fff;
      padding: 20px;
      border-radius: 12px;
      box-shadow: 0px 4px 8px rgba(0,0,0,0.1);
      width: 260px;
    }
    .display {
      width: 100%;
      height: 50px;
      font-size: 1.5rem;
      text-align: right;
      margin-bottom: 15px;
      padding: 5px;
      border: 1px solid #ccc;
      border-radius: 8px;
    }
    .buttons {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 10px;
    }
    button {
      padding: 15px;
      font-size: 1rem;
      border: none;
      border-radius: 8px;
      cursor: pointer;
      background: #e5e7eb;
      transition: 0.2s;
    }
    button:hover {
      background: #d1d5db;
    }
    .operator {
      background: #60a5fa;
      color: white;
    }
    .operator:hover {
      background: #3b82f6;
    }
    .equal {
      grid-column: span 2;
      background: #34d399;
      color: white;
    }
    .equal:hover {
      background: #10b981;
    }
    .clear {
      background: #f87171;
      color: white;
    }
    .clear:hover {
      background: #ef4444;
    }
  </style>
</head>
<body>
  <div class="calculator">
    <input type="text" class="display" id="display" disabled>
    <div class="buttons">
      <button class="clear" onclick="clearDisplay()">C</button>
      <button onclick="appendValue('(')">(</button>
      <button onclick="appendValue(')')">)</button>
      <button class="operator" onclick="appendValue('/')">÷</button><button onclick="appendValue('7')">7</button>
  <button onclick="appendValue('8')">8</button>
  <button onclick="appendValue('9')">9</button>
  <button class="operator" onclick="appendValue('*')">×</button>

  <button onclick="appendValue('4')">4</button>
  <button onclick="appendValue('5')">5</button>
  <button onclick="appendValue('6')">6</button>
  <button class="operator" onclick="appendValue('-')">−</button>

  <button onclick="appendValue('1')">1</button>
  <button onclick="appendValue('2')">2</button>
  <button onclick="appendValue('3')">3</button>
  <button class="operator" onclick="appendValue('+')">+</button>

  <button onclick="appendValue('0')">0</button>
  <button onclick="appendValue('.')">.</button>
  <button class="equal" onclick="calculate()">=</button>
</div>

  </div>  <script>
    let display = document.getElementById('display');

    function appendValue(value) {
      display.value += value;
    }

    function clearDisplay() {
      display.value = '';
    }

    function calculate() {
      try {
        display.value = eval(display.value);
      } catch (e) {
        display.value = 'Error';
      }
    }
  </script></body>
</html>
