
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Code Display and Copy</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
        }
        .code-container {
            position: relative;
            max-width: 600px;
            margin: 0 auto;
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 5px;
            background: #f9f9f9;
            overflow: auto;
        }
        .code-container pre {
            margin: 0;
            white-space: pre-wrap;
            word-wrap: break-word;
        }
        .copy-btn {
            position: absolute;
            top: 10px;
            right: 10px;
            padding: 5px 10px;
            border: none;
            background-color: #007bff;
            color: white;
            border-radius: 3px;
            cursor: pointer;
        }
        .copy-btn:hover {
            background-color: #0056b3;
        }
    </style>
</head>
<body>
    <h1>Code Display and Copy</h1>
    <div class="code-container">
        <button class="copy-btn" onclick="copyCode()">Copy</button>
        <pre id="code">
#include &lt;SoftwareSerial.h&gt;

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
        </pre>
    </div>

    <script>
        function copyCode() {
            const codeElement = document.getElementById('code');
            const range = document.createRange();
            range.selectNode(codeElement);
            window.getSelection().removeAllRanges(); // Clear previous selections
            window.getSelection().addRange(range); // Select the code
            document.execCommand('copy'); // Copy the selection to clipboard
            window.getSelection().removeAllRanges(); // Deselect the code
            alert('Code copied to clipboard!');
        }
    </script>
</body>
</html>
