<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Arduino Projects Showcase</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            background-color: #f0f0f0;
            color: #333;
        }
        header {
            background-color: #007bff;
            color: white;
            padding: 15px 0;
            text-align: center;
        }
        nav {
            display: flex;
            justify-content: center;
            background: #0056b3;
        }
        nav a {
            color: white;
            padding: 14px 20px;
            text-decoration: none;
            text-align: center;
            font-size: 16px;
        }
        nav a:hover {
            background: #003d7a;
        }
        .container {
            max-width: 1000px;
            margin: auto;
            padding: 20px;
        }
        .section {
            margin-bottom: 20px;
            background: white;
            border-radius: 8px;
            padding: 20px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        }
        .project-title {
            color: #007bff;
            margin-top: 0;
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
        .accordion {
            background-color: #007bff;
            color: white;
            cursor: pointer;
            padding: 10px;
            width: 100%;
            border: none;
            text-align: left;
            outline: none;
            font-size: 16px;
            transition: 0.4s;
        }
        .active, .accordion:hover {
            background-color: #0056b3;
        }
        .panel {
            padding: 0 18px;
            display: none;
            overflow: hidden;
            background-color: white;
        }
    </style>
    <script>
        function toggleAccordion(event) {
            const target = event.currentTarget;
            target.classList.toggle('active');
            const panel = target.nextElementSibling;
            if (panel.style.display === "block") {
                panel.style.display = "none";
            } else {
                panel.style.display = "block";
            }
        }
    </script>
</head>
<body>

    <header>
        <h1>Arduino Projects Showcase</h1>
    </header>

    <nav>
        <a href="#project1">Project 1</a>
        <a href="#project2">Project 2</a>
        <a href="#project3">Project 3</a>
        <a href="#project4">Project 4</a>
    </nav>

    <div class="container">
        <div id="project1" class="section">
            <h2 class="project-title">Smart Home System with Arduino</h2>
            <p>This project demonstrates a basic smart home system using an Arduino to control light bulbs and a fan via Bluetooth.</p>
            <button class="accordion">Components Needed</button>
            <div class="panel">
                <ul>
                    <li>Arduino board (e.g., Arduino Uno)</li>
                    <li>HC-05 Bluetooth module</li>
                    <li>Relay module</li>
                    <li>One fan</li>
                    <li>Three light bulbs</li>
                    <li>Jumper wires</li>
                    <li>Power supply</li>
                </ul>
            </div>
            <button class="accordion">Connections</button>
            <div class="panel">
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
            <button class="accordion">Arduino Code</button>
            <div class="panel">
                <p>The Arduino code controls the smart home system. <a href="https://github.com/mrvlegend/Smart-home.git" class="code-button" target="_blank">View Code</a></p>
            </div>
            <button class="accordion">Using the System</button>
            <div class="panel">
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

        <!-- Repeat similar sections for other projects -->
        <div id="project2" class="section">
            <h2 class="project-title">Another Project Title</h2>
            <!-- Project details go here -->
        </div>

        <div id="project3" class="section">
            <h2 class="project-title">Yet Another Project Title</h2>
            <!-- Project details go here -->
        </div>

        <div id="project4" class="section">
            <h2 class="project-title">Final Project Title</h2>
            <!-- Project details go here -->
        </div>
    </div>

</body>
</html>
