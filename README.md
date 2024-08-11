
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Smart Home Setup Guide</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            color: #333;
            background-color: #f4f4f9;
            margin: 0;
            padding: 0;
        }

        header {
            background-color: #0044cc;
            color: #fff;
            padding: 20px 0;
            text-align: center;
        }

        header h1 {
            margin: 0;
            font-size: 24px;
        }

        main {
            padding: 20px;
            max-width: 900px;
            margin: auto;
        }

        section {
            background-color: #fff;
            border: 1px solid #ddd;
            border-radius: 5px;
            margin-bottom: 20px;
            padding: 20px;
            box-shadow: 0 0 10px rgba(0,0,0,0.1);
        }

        section h2 {
            color: #0044cc;
            border-bottom: 2px solid #0044cc;
            padding-bottom: 10px;
            margin-bottom: 20px;
            font-size: 20px;
        }

        ul {
            list-style-type: square;
            padding-left: 20px;
        }

        pre {
            background-color: #f4f4f4;
            border: 1px solid #ddd;
            border-radius: 5px;
            padding: 10px;
            overflow-x: auto;
            font-size: 16px;
        }

        img {
            max-width: 100%;
            height: auto;
            display: block;
            margin: 0 auto 20px;
        }

        footer {
            background-color: #0044cc;
            color: #fff;
            text-align: center;
            padding: 10px 0;
            position: fixed;
            width: 100%;
            bottom: 0;
        }

        center h2 {
            color: #0044cc;
        }
    </style>
</head>
<body>
    <header>
        <h1>Smart Home Setup Guide with Arduino and Bluetooth</h1>
    </header>
    <main>
        <section id="introduction">
            <h2>Introduction</h2>
            <p>Learn how to create a smart home system controlled via Bluetooth using Arduino.</p>
        </section>

        <section id="components">
            <h2>Components Needed</h2>
            <ul>
                <li>Arduino Board</li>
                <li>HC-05 Bluetooth Module</li>
                <li>Relay Module</li>
                <li>Power Supply</li>
                <li>Various Home Appliances (Lights, Fans, etc.)</li>
            </ul>
        </section>

        <section id="wiring">
            <h2>Wiring Diagram</h2>
            <img src="wiring-diagram.png" alt="Wiring Diagram">
            <p>Connect the HC-05 module to the Arduino as follows:</p>
            <ul>
                <li>HC-05 TX to Arduino RX</li>
                <li>HC-05 RX to Arduino TX</li>
                <li>HC-05 VCC to Arduino 5V</li>
                <li>HC-05 GND to Arduino GND</li>
            </ul>
        </section>

        <section id="arduino-code">
            <h2>Arduino Code</h2>
            <pre><code>
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
            

        <section id="testing">
            <h2>Testing the System</h2>
            <p>Pair your Bluetooth device with your smartphone and use a Bluetooth terminal app to send commands to the Arduino.</p>
        </section>

        <section id="troubleshooting">
            <h2>Troubleshooting</h2>
            <p>If you encounter issues, check the following:</p>
            <ul>
                <li>Ensure correct wiring connections.</li>
                <li>Check the baud rate settings on both the Arduino and Bluetooth module.</li>
                <li>Verify the Bluetooth pairing process.</li>
            </ul>
        </section>
    </main>
    
        <p>&copy; 2024 Smart Home Projects</p>
    
    <script src="scripts.js"></script>
 <footer><bottom >  <center><h2>By mr_vlegend</h2></center></footer></bottom>

