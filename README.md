
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Smart Home System with Arduino</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
            background-color: #f0f0f0;
            color: #333;
        }
        h1, h2 {
            color: #007bff;
        }
        .container {
            max-width: 800px;
            margin: auto;
            background: linear-gradient(135deg, #ff9a9e 0%, #fad0c4 100%);
            padding: 20px;
            border-radius: 12px;
            box-shadow: 0 12px 24px rgba(0, 0, 0, 0.2);
            position: relative;
        }
        .section {
            margin-bottom: 20px;
            background: white;
            border-radius: 8px;
            padding: 15px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        }
        .code-button {
            display: inline-block;
            background-color: #007bff;
            color: white;
            border: none;
            padding: 10px 20px;
            cursor: pointer;
            border-radius: 4px;
            text-align: center;
            font-size: 16px;
            text-decoration: none;
            transition: background-color 0.3s;
        }
        .code-button:hover {
            background-color: #0056b3;
        }
        .code-button:focus {
            outline: none;
            box-shadow: 0 0 0 2px rgba(0, 123, 255, 0.5);
        }
    </style>
</head>
<body>

    <div class="container">
        <h1>Smart Home System with Arduino</h1>
        
        <div class="section">
            <h2>Overview</h2>
            <p>This guide provides instructions for setting up a basic smart home system using an Arduino. You will control three light bulbs and one fan via Bluetooth.</p>
        </div>

        <div class="section">
            <h2>Components Needed</h2>
            <ul>
                <li>Arduino board (e.g., Arduino Uno)</li>
                <li>HC-05 Bluetooth module</li>
                <li>relay module</li>
                <li>One fan</li>
                <li>Three light bulbs</li>
                <li>Jumper wires</li>
                <li>Power supply</li>
            </ul>
        </div>

        <div class="section">
            <h2>Connections</h2>
            <p>Follow these steps to connect your components:</p>
            <ul>
                <li><strong>HC-05 Bluetooth Module:</strong>
                    <ul>
                        <li>VCC to 5V (Arduino)</li>
                        <li>GND to Ground (Arduino)</li>
                        <li>TXD to RX (Pin 0, Arduino)</li>
                        <li>RXD to TX (Pin 1, Arduino)</li>
                    </ul>
                </li>
                <li><strong>Relays:</strong>
                    <ul>
                        <li>Relay 1 IN to Pin 2 (Arduino) - Controls Bulb 1</li>
                        <li>Relay 2 IN to Pin 3 (Arduino) - Controls Bulb 2</li>
                        <li>Relay 3 IN to Pin 4 (Arduino) - Controls Bulb 3</li>
                        <li>Relay 4 IN to Pin 5 (Arduino) - Controls Fan</li>
                    </ul>
                </li>
                <li><strong>Devices:</strong>
                    <ul>
                        <li>Connect each bulb to the COM and NO pins of Relays 1, 2, and 3.</li>
                        <li>Connect the fan to the COM and NO pins of Relay 4.</li>
                    </ul>
                </li>
            </ul>
        </div>

        <div class="section">
            <h2>Arduino Code</h2>
            <p>The Arduino code controls the smart home system by receiving commands from the Bluetooth module. To obtain the Arduino code, click the button below:</p>
            <a href="https://github.com/mrvlegend/Smart-home.git" class="code-button" target="_blank">View smart home Code for Arduino </a>
        </div>

        <div class="section">
            <h2>Using the System</h2>
            <p>To control the devices:</p>
            <ul>
                <li>Pair your smartphone with the HC-05 Bluetooth module.</li>
                <li>Use a Bluetooth terminal app or custom app to send commands:</li>
                <ul>
                    <li>Send '1' to turn on Bulb 1</li>
                    <li>Send '2' to turn off Bulb 1</li>
                    <li>Send '3' to turn on Bulb 2</li>
                    <li>Send '4' to turn off Bulb 2</li>
                    <li>Send '5' to turn on Bulb 3</li>
                    <li>Send '6' to turn off Bulb 3</li>
                    <li>Send '7' to turn on the Fan</li>
                    <li>Send '8' to turn off the Fan</li>
                </ul>
            </ul>
        </div>
    </div>

</body>
</html>
