# Calculator-
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Simple Calculator</title>
    <style>
        body {
            background: #f4f4f4;
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
        }
        .calculator {
            background: #fff;
            padding: 20px 30px;
            border-radius: 10px;
            box-shadow: 0 6px 20px rgba(0,0,0,0.1);
            width: 300px;
        }
        .calculator input {
            width: 100%;
            height: 50px;
            font-size: 1.5em;
            margin-bottom: 15px;
            padding: 8px;
            text-align: right;
            border: 1px solid #ddd;
            border-radius: 5px;
            box-sizing: border-box;
        }
        .buttons {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 10px;
        }
        button {
            height: 45px;
            font-size: 1.2em;
            border: none;
            border-radius: 5px;
            background: #eee;
            cursor: pointer;
            transition: background 0.2s;
        }
        button:hover {
            background: #d3d3d3;
        }
        .equal {
            background: #4caf50;
            color: #fff;
        }
        .clear {
            background: #f44336;
            color: #fff;
        }
    </style>
</head>
<body>
    <div class="calculator">
        <input type="text" id="display" readonly>
        <div class="buttons">
            <button onclick="append('7')">7</button>
            <button onclick="append('8')">8</button>
            <button onclick="append('9')">9</button>
            <button onclick="append('/')">÷</button>
            <button onclick="append('4')">4</button>
            <button onclick="append('5')">5</button>
            <button onclick="append('6')">6</button>
            <button onclick="append('*')">×</button>
            <button onclick="append('1')">1</button>
            <button onclick="append('2')">2</button>
            <button onclick="append('3')">3</button>
            <button onclick="append('-')">−</button>
            <button onclick="append('0')">0</button>
            <button onclick="append('.')">.</button>
            <button onclick="calculate()" class="equal">=</button>
            <button onclick="append('+')">+</button>
            <button onclick="clearDisplay()" class="clear" style="grid-column: 1/5;">C</button>
        </div>
    </div>
    <script>
        const display = document.getElementById('display');

        function append(val) {
            display.value += val;
        }

        function clearDisplay() {
            display.value = '';
        }

        function calculate() {
            try {
                display.value = eval(display.value);
            } catch {
                display.value = 'Error';
            }
        }
    </script>
</body>
</html>
