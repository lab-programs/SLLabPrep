# SL Lab

## Program 6.A

```html
<!DOCTYPE html>

<head>
    <title>
        Customer Feedback
    </title>
    <script>
        function displayName() {
            document.getElementById('dname').innerHTML = "NAME: " + document.getElementById('name').value
        }

        function displayGender() {
            if (document.getElementById('male').checked) {
                document.getElementById('dgender').innerHTML = "GENDER: MALE"
            } else {
                document.getElementById('dgender').innerHTML = "GENDER: FEMALE"
            }
        }

        function displayFeedback() {
            document.getElementById('dfeedback').innerHTML = 'FEEDBACK: ' + document.getElementById('feedback').value
        }
    </script>
</head>

<body>
    <h2>Customer Feedback</h2>
    Enter Name:&nbsp;<input type="text" name="name" id="name" placeholder="" onchange="displayName()">
    <br><br> Enter Gender:<br>
    <input type="radio" name="gender" id="male" checked onchange="displayGender()">Male<br>
    <input type="radio" name="gender" id="female" onchange="displayGender()">Female<br>
    <br>Feedback:<br>
    <textarea name="feedback" id="feedback" placeholder="Enter your valuable feedback here..." 
              onchange="displayFeedback()"></textarea>

    <h3>Details</h3>
    <p id='dname'>
        <script>
            displayName()
        </script>
    </p>
    <p id='dgender'>
        <script>
            displayGender()
        </script>
    </p>
    <p id='dfeedback'>
        <script>
            displayFeedback()
        </script>
    </p>
</body>


</html>
```

## Program 7.A

```html
<!DOCTYPE html>

<head>
    <title>Number Validation</title>
    <script>
        function validate() {
            number = document.getElementById('num').value;
            document.getElementById('op').innerHTML = ""
            if (number && number >= 0) {
                if (number % 3 == 0) {
                    document.getElementById('op').innerHTML += (number + ' is divisible by 3<br>')
                } else {
                    document.getElementById('op').innerHTML += (number + ' is not divisible by 3<br>')
                }
                if (number % 7 == 0) {
                    document.getElementById('op').innerHTML += (number + ' is divisible by 7<br>')
                } else {
                    document.getElementById('op').innerHTML += (number + ' is not divisible by 7<br>')
                }
            } else {
                document.getElementById('op').innerHTML = 'Invalid number!'
            }
        }
    </script>
</head>

<body>
    <h2>Number Validation</h2>
    <br><br>Enter number: <input type="number" id="num">
    <input type="submit" name="Submit" onclick="validate()">
    <p id='op'></p>
</body>

</html>
```

## Program 8.A

```html
<!DOCTYPE html>

<head>
    <title>Calculator</title>
    <script>
        function operate() {
            var n1 = parseInt(document.getElementById('num1').value);
            var n2 = parseInt(document.getElementById('num2').value);


            if (n1 && n1 >= 0 && n2 && n2 >= 0) {
                if (document.getElementById('add').checked) {
                    document.getElementById('op').innerHTML = 'Sum: ' + (n1 + n2);
                } else if (document.getElementById('sub').checked) {
                    document.getElementById('op').innerHTML = 'Difference: ' + (n1 - n2);
                } else if (document.getElementById('mul').checked) {
                    document.getElementById('op').innerHTML = 'Product: ' + (n1 * n2);
                } else {
                    if (n2 == 0) {
                        document.getElementById('op').innerHTML = 'Can not divide by zero';
                    } else {
                        document.getElementById('op').innerHTML = 'Quotient: ' + (n1 / n2);
                    }
                }
            } else {
                document.getElementById('op').innerHTML = 'Invalid input!'
            }
        }
    </script>
</head>

<body>
    <h2>Calculator</h2>

    Enter Number 1: <input type="number" id="num1" onchange="operate()">

    <br><br> Enter Number 2: <input type="number" id="num2" onchange="operate()">

    <br><br> Select operation:<br>
    <input type="radio" name="operation" id="add" onchange="operate()" checked>Add<br>
    <input type="radio" name="operation" id="sub" onchange="operate()">Subtract<br>
    <input type="radio" name="operation" id="mul" onchange="operate()">Multiply<br>
    <input type="radio" name="operation" id="div" onchange="operate()">Divide<br>

    <p id='op'>
        <script>
            operate()
        </script>
    </p>
</body>

</html>
```

## Program 9.A

```html
<!DOCTYPE html>

<head>
    <title>
        Longest Word
    </title>
    <script type="text/javascript" src='longestWord.js'></script>
</head>

<body>
    <h2>Web app to find the length of the longest word in a sentence...</h2>
    <textarea id='sentence' placeholder='Enter a sentence here...' rows='20' cols='20'></textarea>
    <input type='submit' name='Submit' onclick='getLength()'>
</body>

</html>
```
```js
function getLength() {
    var sentence = document.getElementById('sentence').value;
    var maxLen = 0;
    sentence = sentence.split(' ');
    console.log(sentence)
    sentence.forEach(function(i) {
        if (maxLen < i.length) {
            maxLen = i.length;
        }
    })
    alert('Length of the longest word = ' + maxLen)
}
```

## Program 10.A

```html
<!-- 1 USD = 73.06 INR -->
<!-- 1 EURO = 88.69 INR -->

<!DOCTYPE html>

<head>
    <title>Currency Convertor!</title>
    <script type="text/javascript" src='conversion.js'>
    </script>
</head>

<body>
    <h3>
        Conversion from USD to INR
    </h3>

    Enter currency in USD:
    <input type='number' id='usdToInr' name='usdToInr'>
    <input type='submit' name='Submit' onclick="convertUsdToInr()">

    <p id='inrValueFromUsd'><br></p>
    <br><br>
    <h3>
        Conversion from INR to USD
    </h3>

    Enter currency in INR:
    <input type='number' id='inrToUsd' name='inrToUsd'>
    <input type='submit' name='Submit' onclick="converInrToUsd()">

    <p id='usdValueFromInr'><br></p>
    <br><br>
    <h3>
        Conversion from EURO to INR
    </h3>

    Enter currency in EURO:
    <input type='number' id='euroToInr' name='euroToInr'>
    <input type='submit' name='Submit' onclick="convertEuroToInr()">

    <p id='inrValueFromEuro'><br></p>
    <br><br>
    <h3>
        Conversion from INR to EURO
    </h3>

    Enter currency in INR:
    <input type='number' id='inrToEuro' name='inrToEuro'>
    <input type='submit' name='Submit' onclick="convertInrToEuro()">

    <p id='euroValueFromInr'><br></p>
</body>

</html>
```

```js
function convertUsdToInr() {
    var usdValue = document.getElementById('usdToInr').value;
    if (usdValue) {
        document.getElementById('inrValueFromUsd').innerHTML = usdValue * 73.06;
    } else {
        document.getElementById('inrValueFromUsd').innerHTML = 'Enter a valid number!'
    }
}

function converInrToUsd() {
    var inrValue = document.getElementById('inrToUsd').value;
    if (inrValue) {
        document.getElementById('usdValueFromInr').innerHTML = inrValue / 73.06;
    } else {
        document.getElementById('usdValueFromInr').innerHTML = 'Enter a valid number!'
    }
}

function convertEuroToInr() {
    var euroValue = document.getElementById('euroToInr').value;
    if (euroValue) {
        document.getElementById('inrValueFromEuro').innerHTML = euroValue * 88.69;
    } else {
        document.getElementById('inrValueFromEuro').innerHTML = 'Enter a valid number!'
    }
}

function convertInrToEuro() {
    var inrValue = document.getElementById('inrToEuro').value;
    if (inrValue) {
        document.getElementById('euroValueFromInr').innerHTML = inrValue / 88.69;
    } else {
        document.getElementById('euroValueFromInr').innerHTML = 'Enter a valid number!'
    }
}
```
