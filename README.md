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
            margin: 5px 0;
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
        document.addEventListener('DOMContentLoaded', () => {
            document.querySelectorAll('.accordion').forEach(button => {
                button.addEventListener('click', function() {
                    this.classList.toggle('active');
                    const panel = this.nextElementSibling;
                    panel.style.display = panel.style.display === "block" ? "none" : "block";
                });
            });
        });
    </script>
</head>
<body>
    <header>
        <h1>Arduino Projects Showcase</h1>
    </header>

    <nav>
        <a href="#smartHome">Smart Home</a>
        <a href="#obstacleAvoidingCar">Obstacle Avoiding Car</a>
        <a href="#lineFollower">Line Follower</a>
        <a href="#autoParkingCar">Auto Parking Car</a>
        <a href""#upcom">k</a>
    </nav>

    <div class="container">
        <!-- Smart Home System Project -->
        <div id="smartHome" class="section">
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
                <p>Connect your components as follows:</p>
                <ul>
                    <li>HC-05 Bluetooth Module:
                        <ul>
                            <li>VCC to 5V (Arduino)</li>
                            <li>GND to Ground (Arduino)</li>
                            <li>TXD to RX (Pin 0, Arduino)</li>
                            <li>RXD to TX (Pin 1, Arduino)</li>
                        </ul>
                    </li>
                    <li>Relays:
                        <ul>
                            <li>Relay 1 IN to Pin 2 (Arduino) - Controls Bulb 1</li>
                            <li>Relay 2 IN to Pin 3 (Arduino) - Controls Bulb 2</li>
                            <li>Relay 3 IN to Pin 4 (Arduino) - Controls Bulb 3</li>
                            <li>Relay 4 IN to Pin 5 (Arduino) - Controls Fan</li>
                        </ul>
                    </li>
                    <li>Devices:
                        <ul>
                            <li>Connect each bulb to the COM and NO pins of Relays 1, 2, and 3.</li>
                            <li>Connect the fan to the COM and NO pins of Relay 4.</li>
                        </ul>
                    </li>
                </ul>
            </div>

            <button class="accordion">Arduino Code</button>
            <div class="panel">
                <p>The Arduino code for this project. <a href="https://github.com/mrvlegend/Smart-home.git" class="code-button" target="_blank">View Code</a></p>
            </div>

            <button class="accordion">Using the System</button>
            <div class="panel">
                <p>To control the devices, pair your smartphone with the HC-05 Bluetooth module and use a Bluetooth terminal app to send commands:</p>
                <ul>
                    <li>'1' to turn on Bulb 1</li>
                    <li>'2' to turn off Bulb 1</li>
                    <li>'3' to turn on Bulb 2</li>
                    <li>'4' to turn off Bulb 2</li>
                    <li>'5' to turn on Bulb 3</li>
                    <li>'6' to turn off Bulb 3</li>
                    <li>'7' to turn on the Fan</li>
                    <li>'8' to turn off the Fan</li>
                </ul>
            </div>
        </div>

        <!-- Obstacle Avoiding Car Project -->
        <div id="obstacleAvoidingCar" class="section">
            <h2 class="project-title">Obstacle Avoiding Car</h2>
            <p>This project involves building a car that can avoid obstacles using ultrasonic sensors.</p>

            <button class="accordion">Components Needed</button>
            <div class="panel">
                <ul>
                    <li>Arduino board (e.g., Arduino Uno)</li>
                    <li>Ultrasonic sensor (HC-SR04)</li>
                    <li>Motor driver module</li>
                    <li>DC motors</li>
                    <li>Wheels</li>
                    <li>Battery pack</li>
                    <li>Jumper wires</li>
                </ul>
            </div>

            <button class="accordion">Connections</button>
            <div class="panel">
                <p>Connect the components as follows:</p>
                <ul>
                    <li>Ultrasonic Sensor:
                        <ul>
                            <li>VCC to 5V (Arduino)</li>
                            <li>GND to Ground (Arduino)</li>
                            <li>TRIG to Pin 9 (Arduino)</li>
                            <li>ECHO to Pin 10 (Arduino)</li>
                        </ul>
                    </li>
                    <li>Motor Driver Module:
                        <ul>
                            <li>IN1 to Pin 3 (Arduino)</li>
                            <li>IN2 to Pin 4 (Arduino)</li>
                            <li>IN3 to Pin 5 (Arduino)</li>
                            <li>IN4 to Pin 6 (Arduino)</li>
                            <li>VCC and GND to Battery Pack</li>
                        </ul>
                    </li>
                </ul>
            </div>

            <button class="accordion">Arduino Code</button>
            <div class="panel">
                <p>The Arduino code for the obstacle avoiding car. <a href="#" class="code-button" target="_blank">View Code</a></p>
            </div>

            <button class="accordion">Using the System</button>
            <div class="panel">
                <p>Upload the code to the Arduino and power the car. It will start moving and avoiding obstacles autonomously.</p>
            </div>
        </div>

        <!-- Line Follower Project -->
        <div id="lineFollower" class="section">
            <h2 class="project-title">Line Follower Car</h2>
            <p>This project involves creating a car that follows a line on the ground using infrared sensors.</p>

            <button class="accordion">Components Needed</button>
            <div class="panel">
                <ul>
                    <li>Arduino board (e.g., Arduino Uno)</li>
                    <li>IR sensors</li>
                    <li>Motor driver module</li>
                    <li>DC motors</li>
                    <li>Wheels</li>
                    <li>Battery pack</li>
                    <li>Jumper wires</li>
                </ul>
            </
