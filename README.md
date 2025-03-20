<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hacking Simulation Game</title>
    
    <!-- CSS: Styling na terminal -->
    <style>
        body {
            background-color: black;
            color: green;
            font-family: monospace;
            text-align: center;
        }

        #terminal {
            width: 80%;
            height: 400px;
            margin: auto;
            border: 2px solid green;
            padding: 10px;
            background-color: black;
            overflow-y: auto;
        }

        #commandInput {
            width: 100%;
            background: black;
            color: green;
            border: none;
            font-size: 18px;
        }
    </style>
</head>
<body>
    <div id="terminal">
        <div id="output">Welcome to Cyber Hack Game!<br>Type "help" to see commands.</div>
        <input type="text" id="commandInput" placeholder="Enter command..." autofocus>
    </div>

    <!-- JavaScript: Aikin Game -->
    <script>
        document.getElementById("commandInput").addEventListener("keydown", function(event) {
            if (event.key === "Enter") {
                let input = this.value.toLowerCase();
                this.value = "";
                processCommand(input);
            }
        });

        function processCommand(input) {
            let outputDiv = document.getElementById("output");

            if (input === "help") {
                outputDiv.innerHTML += "<br>Commands:<br>- scan: Scan for targets<br>- attack: Hack a system<br>- decrypt: Decrypt passwords";
            } else if (input === "scan") {
                outputDiv.innerHTML += "<br>Scanning... Found 3 targets!";
            } else if (input === "attack") {
                outputDiv.innerHTML += "<br>Attacking... Success! System hacked!";
            } else if (input === "decrypt") {
                outputDiv.innerHTML += "<br>Decrypting... Password cracked!";
            } else {
                outputDiv.innerHTML += "<br>Unknown command. Type 'help' to see commands.";
            }
        }
    </script>
</body>
</html>