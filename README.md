<!DOCTYPE html>
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
            background: #f8f8f2;
            color: #007bff;
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
  <h1>Components Needed:</h1>
<p> Bluetooth Module: Such as HC-05 or HC-06 (for communication).
Microcontroller: Arduino, ESP32, or similar (for controlling devices).
Smart Devices: Relays, sensors, or other smart home devices you want to control.
Smartphone or PC: To send Bluetooth commands.
Power Supply: For the microcontroller and modules.</p>
HC-05/HC-06   Arduino
---------------------
VCC           -> 5V
GND           -> GND
TXD           -> RX (Pin 0)
RXD           -> TX (Pin 1)
HC-05/HC-06   ESP32
---------------------
VCC           -> 3.3V
GND           -> GND
TXD           -> RX (GPIO 16)
RXD           -> TX (GPIO 17)

    <div class="code-container">
        <button class="copy-button" onclick="copyToClipboard()">Copy</button>
        <pre><code id="codeBlock">
#include <SoftwareSerial.h>

SoftwareSerial bluetooth(10, 11); // RX, TX
int ledPin = 9; // Pin connected to relay

void setup() {
    bluetooth.begin(9600); // Initialize Bluetooth serial
    pinMode(ledPin, OUTPUT); // Set LED pin as output
}

void loop() {
    if (bluetooth.available()) {
        char command = bluetooth.read(); // Read command from Bluetooth

        if (command == '1') {
            digitalWrite(ledPin, HIGH); // Turn on device
        } else if (command == '0') {
            digitalWrite(ledPin, LOW); // Turn off device
        }
    }
}

        </code></pre>
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
