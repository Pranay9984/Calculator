# Calculator
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        body {
            font-family: Arial, Helvetica, sans-serif;
            background: #f2f2f2;
            justify-content: center;
            align-items: center;
            height: 100vh;
        }
        .calculator {
            background: white;
            padding: 20px;
            border-radius: 1opx;
            width: 260px;
            box-shadow: 0 0 10px rgba(0,0,0,0.2);
            background-color: blueviolet;
        }
        input {
            width: 100%;
            height: 40px;
            font-size: 18px;
            margin-bottom: 10px;
            text-align: right;
        }
        button {
            width: 50px;
            height: 40px;
            margin: 5px;
            font-size: 20px;
            cursor: pointer;
        }
        .row {
            display: flex;
            justify-content: space-between;
        }
    </style>
</head>
<body>
    <div class="calculator">
        <input type="text" id="result" disabled>

        <div class="row">
            <button onclick="clearResult()">C</button>
            <button onclick="appendValue('/')">/</button>
            <button onclick="appendValue('*')">*</button>
            <button onclick="appendValue('-')">-</button>
        </div>
        <div class="row">
            <button onclick="appendValue('7')">7</button>
            <button onclick="appendValue('8')">8</button>
            <button onclick="appendValue('9')">9</button>
            <button onclick="appendValue('+')">+</button>
        </div>
        <div class="row">
            <button onclick="appendValue('4')">4</button>
            <button onclick="appendValue('5')">5</button>
            <button onclick="appendValue('6')">6</button>
            <button onclick="calculate()">=</button>
        </div>
        <div class="row">
            <button onclick="appendValue('3')">3</button>
            <button onclick="appendValue('2')">2</button>
            <button onclick="appendValue('1')">1</button>
            <button onclick="appendValue('0')">0</button>
        </div>
    </div>

    <script>
        function appendValue(value) {
        document.getElementById("result").value += value;
    }

    function clearResult() {
        document.getElementById("result").value = "";
    }

    function calculate() {
        let exp = document.getElementById("result").value;
        try {
            document.getElementById("result").value = eval(exp);
        } catch {
            document.getElementById("result").value = "Error";
        }
    }
    </script>
</body>
</html>
