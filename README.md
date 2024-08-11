
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Smart Home Setup Guide</title>
    <link rel="stylesheet" href="styles.css">
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

SoftwareSerial BTSerial(10, 11); // RX | TX

void setup() {
    BTSerial.begin(9600);  // HC-05 Bluetooth module baud rate
    Serial.begin(9600);    // Serial monitor baud rate
}

void loop() {
    if (BTSerial.available()) {
        char command = BTSerial.read();
        if (command == '1') {
            // Code to turn on the device
            Serial.println("Device ON");
        } else if (command == '0') {
            // Code to turn off the device
            Serial.println("Device OFF");
        }
    }
}
            </code></pre>
        </section>

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
    <footer>
        <p>&copy; 2024 Smart Home Projects</p>
    </footer>
    <script src="scripts.js"></script>
</body>
</html>
