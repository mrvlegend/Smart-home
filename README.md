<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Smart Home Showcase</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <header>
        <h1>Smart Home Showcase</h1>
    </header>

    <main>
        <section class="image-section">
            <img src="https://images.unsplash.com/photo-1587996401562-7760384b2f4d" alt="Smart Home" class="smart-home-image">
        </section>

        <section class="code-section">
            <h2>Code Example</h2>
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
            <button onclick="copyCode()">Copy</button>
        </section>

        <footer>
            <p>Developed by Your Name</p>
        </footer>
    </main>

    <script>
        function copyCode() {
            const codeElement = document.getElementById('code');
            const range = document.createRange();
            range.selectNode(codeElement);
            window.getSelection().removeAllRanges();
            window.getSelection().addRange(range);
            try {
                document.execCommand('copy');
                alert('Code copied to clipboard!');
            } catch (err) {
                alert('Failed to copy code.');
            }
            window.getSelection().removeAllRanges();
        }
    </script>
</body>
</html>
