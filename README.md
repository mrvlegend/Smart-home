
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Colorful Code Display with Copy Button</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
            background-color: #f0f0f0;
        }
        .code-container {
            position: relative;
            margin-bottom: 20px;
            border: 2px solid #007bff;
            border-radius: 8px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
            background-color: #fff;
        }
        .code-container pre {
            background: #2e2e2e;
            color: #f8f8f2;
            padding: 15px;
            margin: 0;
            overflow-x: auto;
            border-radius: 8px 8px 0 0;
            font-size: 16px;
            font-family: 'Courier New', Courier, monospace;
        }
        .copy-button {
            position: absolute;
            top: 10px;
            right: 10px;
            background-color: #28a745;
            color: white;
            border: none;
            padding: 8px 15px;
            cursor: pointer;
            border-radius: 4px;
            font-size: 14px;
        }
        .copy-button:hover {
            background-color: #218838;
        }
        .code-container pre code {
            display: block;
            white-space: pre-wrap;
            word-break: break-word;
        }
    </style>
</head>
<body>

    <h1>Colorful Code Display Example</h1>

    <div class="code-container">
        <button class="copy-button" onclick="copyToClipboard()">Copy</button>
        #include <SoftwareSerial.h>

// Set up Bluetooth serial communication
SoftwareSerial bluetooth(10, 11); // RX, TX

// Pin definitions
const int ledPin1 = 2; // LED 1
const int ledPin2 = 3; // LED 2
const int ledPin3 = 4; // LED 3
const int fanPin = 5;  // Relay control for the fan

void setup() {
    // Start serial communication with the computer and Bluetooth module
    Serial.begin(9600);
    bluetooth.begin(9600);

    // Set LED and relay pins as outputs
    pinMode(ledPin1, OUTPUT);
    pinMode(ledPin2, OUTPUT);
    pinMode(ledPin3, OUTPUT);
    pinMode(fanPin, OUTPUT);

    // Initialize LEDs and fan to OFF
    digitalWrite(ledPin1, LOW);
    digitalWrite(ledPin2, LOW);
    digitalWrite(ledPin3, LOW);
    digitalWrite(fanPin, LOW); // Fan OFF
}

void loop() {
    // Check if data is available from Bluetooth
    if (bluetooth.available()) {
        char command = bluetooth.read();
        
        // Process the received command
        switch (command) {
            case '1': // Turn on LED 1
                digitalWrite(ledPin1, HIGH);
                bluetooth.print("LED 1 ON\n");
                break;
            case '2': // Turn off LED 1
                digitalWrite(ledPin1, LOW);
                bluetooth.print("LED 1 OFF\n");
                break;
            case '3': // Turn on LED 2
                digitalWrite(ledPin2, HIGH);
                bluetooth.print("LED 2 ON\n");
                break;
            case '4': // Turn off LED 2
                digitalWrite(ledPin2, LOW);
                bluetooth.print("LED 2 OFF\n");
                break;
            case '5': // Turn on LED 3
                digitalWrite(ledPin3, HIGH);
                bluetooth.print("LED 3 ON\n");
                break;
            case '6': // Turn off LED 3
                digitalWrite(ledPin3, LOW);
                bluetooth.print("LED 3 OFF\n");
                break;
            case 'F': // Turn on Fan
                digitalWrite(fanPin, HIGH);
                bluetooth.print("Fan ON\n");
                break;
            case 'f': // Turn off Fan
                digitalWrite(fanPin, LOW);
                bluetooth.print("Fan OFF\n");
                break;
            default:
                bluetooth.print("Unknown command\n");
                break;
        }
    }
}
        

    </div>

    <script>
        function copyToClipboard() {
            const code = document.getElementById('codeBlock').innerText;
            navigator.clipboard.writeText(code).then(() => {
                alert('Code copied to clipboard!');
            }).catch(err => {
                console.error('Failed to copy code: ', err);
            });
        }
    </script>

</body>
</html>
