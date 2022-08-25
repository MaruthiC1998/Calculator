<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calculator</title>
    <style>
        .display {
            border: 1px solid black;
            height: 50px;
            width: 220px;
            display: flex;
            justify-content: end;
            align-items: end;
            background-color: darkgray;
            color: brown;
            border-radius: 10px;
            border-color:black;
            font-size: 30px;
        }

        button {
            height: 50px;
            width: 50px;
            background-color: darkgray;
            color :black;
            border-radius: 10px;
            font-size: 20px;
            border: 1px solid black;
        }

        #equal {
            height: 99px;
        }

        .container {
            margin-top: 100px;
        }

        h1 {
            background-color: aqua;
            width: 250px;
            border-radius: 10px;
            padding-top: 5px;
            padding-bottom: 5px;
        }
    </style>
</head>

<body>
    <center>
        <div class="container">
            <h1>CALCULATOR</h1>
            <div class="display"></div>
            <table>
                <tr>
                    <td><button id="clear">C</button></td>
                    <td><button id="/">/</button></td>
                    <td><button id="*">X</button></td>
                    <td><button id="back"> < </button>
                    </td>
                </tr>
                <tr>
                    <td><button id="7">7</button></td>
                    <td><button id="8">8</button></td>
                    <td><button id="9">9</button></td>
                    <td><button id="+">+</button></td>
                </tr>
                <tr>
                    <td><button id="4">4</button></td>
                    <td><button id="5">5</button></td>
                    <td><button id="6">6</button></td>
                    <td><button id="-">-</button></td>
                </tr>
                <tr>
                    <td><button id="1">1</button></td>
                    <td><button id="2">2</button></td>
                    <td><button id="3">3</button></td>
                    <td rowspan="2"><button id="equal">=</button></td>
                </tr>
                <tr>
                    <td><button id="(">(</button></td>
                    <td><button id="0">0</button></td>
                    <td><button id=")">)</button></td>
                </tr>
            </table>
        </div>
    </center>
    <script>
        let display = document.querySelector('.display')
        let button = document.querySelectorAll('button')
        button.forEach((btn) => {
            btn.onclick = () => {
                if (btn.id == 'clear') {
                    display.innerText = ''
                }
                else if (btn.id == 'back') {
                    let string = display.innerText.toString()
                    display.innerText = string.slice(0, -1)
                }
                else if (btn.id == 'equal' && display.innerText == '') {
                    display.innerText = 'Empty'
                    setTimeout(() => { display.innerText = "" })
                }
                else if (display.innerText != '' && btn.id == 'equal') {
                    display.innerText = eval(display.innerText)
                }
                else {
                    display.innerText = display.innerText + btn.id
                }
            }
        })

    </script>
</body>

</html>
