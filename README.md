# calcualtor

<html lang="en">
<head>
<meta charset="UTF-8">
<title>Light Calculator</title>
<style>
    body {
        height: 100vh;
        display: flex;
        justify-content: center;
        align-items: center;
        background: linear-gradient(135deg, #e0f7fa, #f1f8ff);
        font-family: 'Segoe UI', sans-serif;
    }

    .calculator {
        width: 320px;
        background: #ffffff;
        border-radius: 20px;
        box-shadow: 0 20px 40px rgba(0, 0, 0, 0.15);
        padding: 20px;
    }

    .display {
        width: 100%;
        height: 60px;
        border: none;
        background: #f5f7fa;
        border-radius: 12px;
        text-align: right;
        padding: 15px;
        font-size: 26px;
        font-weight: bold;
        margin-bottom: 15px;
        outline: none;
    }

    .buttons {
        display: grid;
        grid-template-columns: repeat(4, 1fr);
        gap: 12px;
    }

    button {
        height: 55px;
        border: none;
        border-radius: 12px;
        font-size: 18px;
        font-weight: 600;
        cursor: pointer;
        transition: all 0.2s ease;
        background: #e9eef3;
    }

    button:hover {
        transform: translateY(-2px);
        box-shadow: 0 5px 10px rgba(0, 0, 0, 0.15);
    }

    button:active {
        transform: scale(0.96);
    }

    .operator {
        background: #4dabf7;
        color: white;
    }

    .equal
    </style>
</head>
<body>

<div class="calculator">
    <input type="text" id="display" disabled>

    <div class="buttons">
        <button onclick="clearDisplay()">C</button>
        <button onclick="append('/')">/</button>
        <button onclick="append('*')">*</button>
        <button onclick="append('-')">-</button>

        <button onclick="append('7')">7</button>
        <button onclick="append('8')">8</button>
        <button onclick="append('9')">9</button>
        <button onclick="append('+')">+</button>

        <button onclick="append('4')">4</button>
        <button onclick="append('5')">5</button>
        <button onclick="append('6')">6</button>
        <button onclick="calculate()">=</button>

        <button onclick="append('1')">1</button>
        <button onclick="append('2')">2</button>
        <button onclick="append('3')">3</button>
        <button onclick="append('0')" class="zero">0</button>
    </div>
</div>

<script>
    let display = document.getElementById("display");

    function append(value) {
        display.value += value;
    }

    function clearDisplay() {
        display.value = "";
    }

    function calculate() {
        try {
            display.value = eval(display.value);
        } catch {
            display.value = "Error";
        }
    }
</script>

</body>

